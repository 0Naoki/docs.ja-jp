---
title: SqlMetal.exe (コード生成ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: 94ed6328857f6e77cea150d69719322d3aaaea69
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396923"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="e7295-102">SqlMetal.exe (コード生成ツール)</span><span class="sxs-lookup"><span data-stu-id="e7295-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="e7295-103">SqlMetal コマンド ライン ツールは、 [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] の [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]コンポーネント用のコードとマッピングを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e7295-104">このトピックで後述するオプションを適用することにより、次のようなアクションを SqlMetal で実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7295-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="e7295-105">データベースから、ソース コードとマッピング属性またはマッピング ファイルを生成する。</span><span class="sxs-lookup"><span data-stu-id="e7295-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="e7295-106">データベースから、カスタマイズ用の中間的なデータベース マークアップ言語 (.dbml) ファイルを生成する。</span><span class="sxs-lookup"><span data-stu-id="e7295-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="e7295-107">.dbml ファイルから、コードとマッピング属性またはマッピング ファイルを生成する。</span><span class="sxs-lookup"><span data-stu-id="e7295-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="e7295-108">このツールは、Visual Studio と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e7295-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="e7295-109">既定では、このファイルは `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin にあります。</span><span class="sxs-lookup"><span data-stu-id="e7295-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="e7295-110">Visual Studio をインストールしない場合は、 [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225)をダウンロードすることによって SQLMetal ファイルを入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7295-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7295-111">Visual Studio を使用している開発者は、 [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] を使ってエンティティ クラスを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7295-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="e7295-112">コマンド ライン方式は、大きなデータベースにも適切に対応できます。</span><span class="sxs-lookup"><span data-stu-id="e7295-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="e7295-113">SqlMetal はコマンド ライン ツールであるため、ビルド プロセスでこれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7295-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="e7295-114">このツールを実行するには、開発者コマンド プロンプト (または、Windows 7 の Visual Studio コマンド プロンプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7295-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="e7295-115">詳細については、「[Visual Studio 用開発者コマンド プロンプト](../../../docs/framework/tools/developer-command-prompt-for-vs.md)」を参照してください。コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e7295-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7295-116">構文</span><span class="sxs-lookup"><span data-stu-id="e7295-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="e7295-117">オプション</span><span class="sxs-lookup"><span data-stu-id="e7295-117">Options</span></span>  
 <span data-ttu-id="e7295-118">最新のオプションの一覧を確認するには、コマンド プロンプトでインストール場所に移動し、「 `sqlmetal /?` 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7295-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="e7295-119">**接続オプション**</span><span class="sxs-lookup"><span data-stu-id="e7295-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="e7295-120">オプション</span><span class="sxs-lookup"><span data-stu-id="e7295-120">Option</span></span>|<span data-ttu-id="e7295-121">説明</span><span class="sxs-lookup"><span data-stu-id="e7295-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7295-122">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="e7295-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="e7295-123">データベース サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="e7295-124">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="e7295-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="e7295-125">サーバー上のデータベース カタログを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="e7295-126">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="e7295-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="e7295-127">ログオン ユーザー ID を指定します。既定値は、Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7295-127">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="e7295-128">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="e7295-128">**/password:** *\<password>*</span></span>|<span data-ttu-id="e7295-129">ログオン パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-129">Specifies logon password.</span></span> <span data-ttu-id="e7295-130">既定値は、Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7295-130">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="e7295-131">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="e7295-131">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="e7295-132">データベース接続文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-132">Specifies database connection string.</span></span> <span data-ttu-id="e7295-133">**/server**、 **/database**、 **/user**、または **/password** オプションと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7295-133">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="e7295-134">接続文字列にファイル名は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="e7295-134">Do not include the file name in the connection string.</span></span> <span data-ttu-id="e7295-135">代わりに、コマンド ラインにファイル名を入力ファイルとして追加します。</span><span class="sxs-lookup"><span data-stu-id="e7295-135">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="e7295-136">たとえば、 **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** というコマンド ラインは、入力ファイルとして "c:\northwnd.mdf" を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-136">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="e7295-137">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="e7295-137">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="e7295-138">SqlMetal がデータベースにアクセスする際のタイムアウト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-138">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="e7295-139">既定値は 0 (時間制限なし) です。</span><span class="sxs-lookup"><span data-stu-id="e7295-139">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="e7295-140">**抽出オプション**</span><span class="sxs-lookup"><span data-stu-id="e7295-140">**Extraction options**</span></span>  
  
|<span data-ttu-id="e7295-141">オプション</span><span class="sxs-lookup"><span data-stu-id="e7295-141">Option</span></span>|<span data-ttu-id="e7295-142">説明</span><span class="sxs-lookup"><span data-stu-id="e7295-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7295-143">**/views**</span><span class="sxs-lookup"><span data-stu-id="e7295-143">**/views**</span></span>|<span data-ttu-id="e7295-144">データベース ビューを抽出します。</span><span class="sxs-lookup"><span data-stu-id="e7295-144">Extracts database views.</span></span>|  
|<span data-ttu-id="e7295-145">**/functions**</span><span class="sxs-lookup"><span data-stu-id="e7295-145">**/functions**</span></span>|<span data-ttu-id="e7295-146">データベース関数を抽出します。</span><span class="sxs-lookup"><span data-stu-id="e7295-146">Extracts database functions.</span></span>|  
|<span data-ttu-id="e7295-147">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="e7295-147">**/sprocs**</span></span>|<span data-ttu-id="e7295-148">ストアド プロシージャを抽出します。</span><span class="sxs-lookup"><span data-stu-id="e7295-148">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="e7295-149">**出力オプション**</span><span class="sxs-lookup"><span data-stu-id="e7295-149">**Output options**</span></span>  
  
|<span data-ttu-id="e7295-150">オプション</span><span class="sxs-lookup"><span data-stu-id="e7295-150">Option</span></span>|<span data-ttu-id="e7295-151">説明</span><span class="sxs-lookup"><span data-stu-id="e7295-151">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7295-152">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="e7295-152">**/dbml** *[:file]*</span></span>|<span data-ttu-id="e7295-153">出力を .dbml として送ります。</span><span class="sxs-lookup"><span data-stu-id="e7295-153">Sends output as .dbml.</span></span> <span data-ttu-id="e7295-154">**/map** オプションと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7295-154">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="e7295-155">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="e7295-155">**/code** *[:file]*</span></span>|<span data-ttu-id="e7295-156">出力をソース コードとして送ります。</span><span class="sxs-lookup"><span data-stu-id="e7295-156">Sends output as source code.</span></span> <span data-ttu-id="e7295-157">**/dbml** オプションと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7295-157">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="e7295-158">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="e7295-158">**/map** *[:file]*</span></span>|<span data-ttu-id="e7295-159">属性ではなく XML マッピング ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-159">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="e7295-160">**/dbml** オプションと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7295-160">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="e7295-161">**その他**</span><span class="sxs-lookup"><span data-stu-id="e7295-161">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="e7295-162">オプション</span><span class="sxs-lookup"><span data-stu-id="e7295-162">Option</span></span>|<span data-ttu-id="e7295-163">説明</span><span class="sxs-lookup"><span data-stu-id="e7295-163">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7295-164">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="e7295-164">**/language:** *\<language>*</span></span>|<span data-ttu-id="e7295-165">ソース コードの言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-165">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="e7295-166">Valid *\<language>*: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="e7295-166">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="e7295-167">既定値は、コード ファイル名の拡張子から派生します。</span><span class="sxs-lookup"><span data-stu-id="e7295-167">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="e7295-168">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="e7295-168">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="e7295-169">生成されるコードの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-169">Specifies namespace of the generated code.</span></span> <span data-ttu-id="e7295-170">既定値は、名前空間なしです。</span><span class="sxs-lookup"><span data-stu-id="e7295-170">Default value: no namespace.</span></span>|  
|<span data-ttu-id="e7295-171">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="e7295-171">**/context:** *\<type>*</span></span>|<span data-ttu-id="e7295-172">データ コンテキスト クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-172">Specifies name of data context class.</span></span> <span data-ttu-id="e7295-173">既定値は、データベース名から派生します。</span><span class="sxs-lookup"><span data-stu-id="e7295-173">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="e7295-174">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="e7295-174">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="e7295-175">生成されるコード内のエンティティ クラスの基本クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-175">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="e7295-176">既定値は、エンティティの基本クラスなしです。</span><span class="sxs-lookup"><span data-stu-id="e7295-176">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="e7295-177">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="e7295-177">**/pluralize**</span></span>|<span data-ttu-id="e7295-178">クラスとメンバーの名前を自動的に複数化または単数化します。</span><span class="sxs-lookup"><span data-stu-id="e7295-178">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="e7295-179">このオプションは、米国英語バージョンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7295-179">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="e7295-180">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="e7295-180">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="e7295-181">シリアル化可能なクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-181">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="e7295-182">Valid *\<option>*: Non、Unidirectional。</span><span class="sxs-lookup"><span data-stu-id="e7295-182">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="e7295-183">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="e7295-183">Default value: None.</span></span><br /><br /> <span data-ttu-id="e7295-184">詳細については、「[Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md)」 (シリアル化) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7295-184">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="e7295-185">**入力ファイル**</span><span class="sxs-lookup"><span data-stu-id="e7295-185">**Input File**</span></span>  
  
|<span data-ttu-id="e7295-186">オプション</span><span class="sxs-lookup"><span data-stu-id="e7295-186">Option</span></span>|<span data-ttu-id="e7295-187">説明</span><span class="sxs-lookup"><span data-stu-id="e7295-187">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7295-188">**\<入力ファイル>**</span><span class="sxs-lookup"><span data-stu-id="e7295-188">**\<input file>**</span></span>|<span data-ttu-id="e7295-189">SQL Server Express .mdf ファイル、 [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf ファイル、または .dbml 中間ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7295-189">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7295-190">コメント</span><span class="sxs-lookup"><span data-stu-id="e7295-190">Remarks</span></span>  
 <span data-ttu-id="e7295-191">SqlMetal の実際の機能には、次の 2 つの段階が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7295-191">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="e7295-192">データベースのメタデータを .dbml ファイルに抽出する。</span><span class="sxs-lookup"><span data-stu-id="e7295-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="e7295-193">コード出力ファイルを生成する。</span><span class="sxs-lookup"><span data-stu-id="e7295-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="e7295-194">適切なコマンド ライン オプションを使用することで、Visual Basic または C# ソース コードを生成するか、XML マッピング ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="e7295-194">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="e7295-195">メタデータを .mdf ファイルから抽出するには、他のすべてのオプションの後に .mdf ファイルの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7295-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="e7295-196">**/server** を指定しない場合、 **localhost/sqlexpress** と見なされます。</span><span class="sxs-lookup"><span data-stu-id="e7295-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="e7295-197">次の条件が少なくとも 1 つ満たされる場合、[!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)] は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="e7295-197">[!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)] throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="e7295-198">自身を呼び出すストアド プロシージャを SqlMetal が抽出しようとした。</span><span class="sxs-lookup"><span data-stu-id="e7295-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="e7295-199">ストアド プロシージャ、関数、またはビューの入れ子レベルが 32 を超える。</span><span class="sxs-lookup"><span data-stu-id="e7295-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="e7295-200">SqlMetal はこの例外をキャッチして、それを警告として報告します。</span><span class="sxs-lookup"><span data-stu-id="e7295-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="e7295-201">入力ファイル名を指定するには、その名前をコマンド ラインに入力ファイルとして追加します。</span><span class="sxs-lookup"><span data-stu-id="e7295-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="e7295-202">( **/conn** オプションを使用して) 接続文字列にファイル名を含める操作は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e7295-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7295-203">使用例</span><span class="sxs-lookup"><span data-stu-id="e7295-203">Examples</span></span>  
 <span data-ttu-id="e7295-204">抽出された SQL メタデータを格納する .dbml ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="e7295-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="e7295-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="e7295-206">SQL Server Express を使用して .mdf ファイルから抽出された SQL メタデータを格納する .dbml ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="e7295-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="e7295-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="e7295-208">SQL Server Express から抽出された SQL メタデータを格納する .dbml ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="e7295-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="e7295-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="e7295-210">.dbml メタデータ ファイルからソース コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="e7295-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="e7295-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="e7295-212">SQL メタデータからソース コードを直接生成します。</span><span class="sxs-lookup"><span data-stu-id="e7295-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="e7295-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="e7295-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7295-214">サンプル データベース Northwind で **/pluralize** オプションを使用する場合には、注意を必要とする動作があります。</span><span class="sxs-lookup"><span data-stu-id="e7295-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="e7295-215">SqlMetal がテーブルのために行型の名前を生成するとき、テーブル名は単数形です。</span><span class="sxs-lookup"><span data-stu-id="e7295-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="e7295-216">テーブルに関する <xref:System.Data.Linq.DataContext> プロパティを生成するときには、テーブル名は複数形です。</span><span class="sxs-lookup"><span data-stu-id="e7295-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="e7295-217">偶然にも、サンプル データベース Northwind 内のテーブルには既に複数形が使われています。</span><span class="sxs-lookup"><span data-stu-id="e7295-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="e7295-218">このため、この部分はうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="e7295-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="e7295-219">データベース テーブルの名前は単数形にするのが一般的ですが、.NET では、コレクションの名前を複数形にすることも一般的です。</span><span class="sxs-lookup"><span data-stu-id="e7295-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7295-220">参照</span><span class="sxs-lookup"><span data-stu-id="e7295-220">See Also</span></span>  
 [<span data-ttu-id="e7295-221">方法: Visual Basic または C# でオブジェクト モデルを生成する</span><span class="sxs-lookup"><span data-stu-id="e7295-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 [<span data-ttu-id="e7295-222">LINQ to SQL でのコード生成</span><span class="sxs-lookup"><span data-stu-id="e7295-222">Code Generation in LINQ to SQL</span></span>](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="e7295-223">外部マップ</span><span class="sxs-lookup"><span data-stu-id="e7295-223">External Mapping</span></span>](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
