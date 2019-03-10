---
title: '方法: MaskedTextBox コントロールにデータをバインドします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: b03eff45b8494253918ae4462c29f50568c81569
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717467"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="bfbc2-102">方法: MaskedTextBox コントロールにデータをバインドします。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="bfbc2-103">データをバインドすることができます、<xref:System.Windows.Forms.MaskedTextBox>他の Windows フォーム コントロールと同様に制御します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="bfbc2-104">ただし、データベース内のデータの形式で、マスクの定義で予期される形式が一致しない場合は、データの書式を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="bfbc2-105">次の手順を使用してこれを行う方法を示して、<xref:System.Windows.Forms.Binding.Format>と<xref:System.Windows.Forms.Binding.Parse>のイベント、<xref:System.Windows.Forms.Binding>クラスを別の電話番号を表示および編集可能なフィールドを 1 つとして、拡張データベースのフィールドを電話します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="bfbc2-106">次の手順では、インストールされている Northwind サンプル データベースで SQL Server データベースへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="bfbc2-107">MaskedTextBox コントロールにデータをバインドするには</span><span class="sxs-lookup"><span data-stu-id="bfbc2-107">To bind data to a MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="bfbc2-108">新しい Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-108">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="bfbc2-109">2 つをドラッグ<xref:System.Windows.Forms.TextBox>コントロールをフォームに名前を付けます`FirstName`と`LastName`します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3.  <span data-ttu-id="bfbc2-110">ドラッグ、<xref:System.Windows.Forms.MaskedTextBox>コントロールをフォームには、名前を付けます`PhoneMask`します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4.  <span data-ttu-id="bfbc2-111">設定、<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティの`PhoneMask`に`(000) 000-0000 x9999`します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5.  <span data-ttu-id="bfbc2-112">次の名前空間のインポートをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6.  <span data-ttu-id="bfbc2-113">フォームを右クリックし **コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="bfbc2-114">このコードをフォーム クラスに置きます。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7.  <span data-ttu-id="bfbc2-115">イベント ハンドラーを追加、<xref:System.Windows.Forms.Binding.Format>と<xref:System.Windows.Forms.Binding.Parse>したり分割したりするイベント、`PhoneNumber`と`Extension`、バインドからフィールド<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8.  <span data-ttu-id="bfbc2-116">2 つ追加<xref:System.Windows.Forms.Button>フォームのコントロール。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="bfbc2-117">名前を付けます`previousButton`と`nextButton`します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="bfbc2-118">追加するには、各ボタンをダブルクリックして、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー、およびイベント ハンドラーに次のコード例で示すように入力します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="bfbc2-119">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-119">Run the sample.</span></span> <span data-ttu-id="bfbc2-120">データを編集して、**前**と**次**ボタンのデータが適切に保持されることを確認、 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfbc2-121">例</span><span class="sxs-lookup"><span data-stu-id="bfbc2-121">Example</span></span>  
 <span data-ttu-id="bfbc2-122">次のコード例は、コード全体を前の手順を完了には、その結果の一覧です。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](~/samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](~/samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bfbc2-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="bfbc2-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="bfbc2-124">ビジュアルを作成するC#または Visual Basic プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-124">Create a Visual C# or Visual Basic project.</span></span>  
  
-   <span data-ttu-id="bfbc2-125">追加、<xref:System.Windows.Forms.TextBox>と<xref:System.Windows.Forms.MaskedTextBox>フォームにコントロールを前の手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
-   <span data-ttu-id="bfbc2-126">プロジェクトの既定のフォームのソース コード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-126">Open the source code file for the project's default form.</span></span>  
  
-   <span data-ttu-id="bfbc2-127">このファイル内のソース コードを前の"Code"セクションに記載されているコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
-   <span data-ttu-id="bfbc2-128">アプリケーションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="bfbc2-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbc2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfbc2-129">See also</span></span>
- [<span data-ttu-id="bfbc2-130">チュートリアル: MaskedTextBox コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="bfbc2-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
