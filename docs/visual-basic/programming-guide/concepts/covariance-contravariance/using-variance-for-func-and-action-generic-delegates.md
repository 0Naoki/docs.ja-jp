---
title: "Func および Action 汎用デリゲート (Visual Basic) に対する分散の使用"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b8f9b2ebf758bc0d67b2b623038a4beeb7149261
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a>Func および Action 汎用デリゲート (Visual Basic) に対する分散の使用
以下の例では、`Func` 汎用デリゲートと `Action` 汎用デリゲートの共変性と反変性を使用して、メソッドの再利用を可能にし、コードの柔軟性を高める方法を示します。  
  
 共変性と反変性の詳細については、次を参照してください。[デリゲート (Visual Basic) の分散](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)です。  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>デリゲートと共変の型パラメーターの使用  
 次の例は、`Func` 汎用デリゲートにおける共変性のサポートの利点を示しています。 `FindByTitle` メソッドは、`String` 型のパラメーターを受け取り、`Employee` 型のオブジェクトを返します。 ただし、このメソッドは `Func(Of String, Person)` デリゲートに割り当てることもできます。これは `Employee` が `Person` を継承するためです。  
  
```vb  
' Simple hierarchy of classes.  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class Finder  
    Public Shared Function FindByTitle(  
        ByVal title As String) As Employee  
        ' This is a stub for a method that returns  
        ' an employee that has the specified title.  
        Return New Employee  
    End Function  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim findEmployee As Func(Of String, Employee) =  
            AddressOf FindByTitle  
  
        ' The delegate expects a method to return Person,  
        ' but you can assign it a method that returns Employee.  
        Dim findPerson As Func(Of String, Person) =  
            AddressOf FindByTitle  
  
        ' You can also assign a delegate   
        ' that returns a more derived type to a delegate   
        ' that returns a less derived type.  
        findPerson = findEmployee  
    End Sub  
End Class  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>デリゲートと反変の型パラメーターの使用  
 次の例は、`Action` 汎用デリゲートにおける反変性のサポートの利点を示しています。 `AddToContacts` メソッドは、`Person` 型のパラメーターを受け取ります。 ただし、このメソッドは `Action(Of Employee)` デリゲートに割り当てることもできます。これは `Employee` が `Person` を継承するためです。  
  
```vb  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class AddressBook  
    Shared Sub AddToContacts(ByVal person As Person)  
        ' This method adds a Person object  
        ' to a contact list.  
    End Sub  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim addPersonToContacts As Action(Of Person) =  
            AddressOf AddToContacts  
  
        ' The Action delegate expects   
        ' a method that has an Employee parameter,  
        ' but you can assign it a method that has a Person parameter  
        ' because Employee derives from Person.  
        Dim addEmployeeToContacts As Action(Of Employee) =  
            AddressOf AddToContacts  
  
        ' You can also assign a delegate   
        ' that accepts a less derived parameter   
        ' to a delegate that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>関連項目  
 [共変性と反変性 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)  
 [ジェネリック](~/docs/standard/generics/index.md)
