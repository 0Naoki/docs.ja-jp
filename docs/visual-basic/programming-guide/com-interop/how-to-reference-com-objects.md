---
title: '方法 : Visual Basic から COM オブジェクトを参照する'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 293bf76b1520f50e67837942eab2f27a49e330e3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204787"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>方法 : Visual Basic から COM オブジェクトを参照する
Visual basic でタイプ ライブラリがある COM オブジェクトへの参照を追加する必要があります相互運用機能アセンブリの作成、COM ライブラリの。 COM オブジェクトのメンバーへの参照は、相互運用機能アセンブリにルーティングされ、実際の COM オブジェクトに転送されます。 COM オブジェクトからの応答が相互運用機能アセンブリにルーティングされ、転送、[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]アプリケーション。  
  
 .NET アセンブリに COM オブジェクトの型情報を埋め込むことで、相互運用機能アセンブリを使用せず、COM オブジェクトを参照できます。 型情報を埋め込むには、次のように設定します。、`Embed Interop Types`プロパティを`True`の COM オブジェクトへの参照。 コマンド ライン コンパイラを使用してコンパイルする場合は、使用、 `/link` COM ライブラリを参照するにはオプションです。 詳細については、次を参照してください。 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)します。  
  
 Visual Basic は、統合開発環境 (IDE) からタイプ ライブラリへの参照を追加すると、相互運用機能アセンブリを自動的に作成されます。 コマンドラインから作業をするときは、相互運用機能アセンブリを手動で作成するのに、Tlbimp ユーティリティを使用できます。  
  
### <a name="to-add-references-to-com-objects"></a>COM オブジェクトへの参照を追加するには  
  
1.  **プロジェクト** メニューの 選択**参照の追加** をクリックし、 **COM**  ダイアログ ボックスのタブ。  
  
2.  COM オブジェクトの一覧から使用するコンポーネントを選択します。  
  
3.  相互運用機能アセンブリへのアクセスを簡素化するには、追加、`Imports`ステートメントは、クラスや COM オブジェクトを使用するモジュールの先頭にします。 たとえば、次のコード例は名前空間をインポート`INKEDLib`で参照されるオブジェクトの`Microsoft InkEdit Control 1.0`ライブラリ。  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Tlbimp を使用して相互運用機能アセンブリを作成するには  
  
1.  ない検索パスの一部と、現在では、ディレクトリがある場合は、検索パスに Tlbimp の場所を追加します。  
  
2.  コマンド プロンプトで、次の情報を提供するには、Tlbimp を呼び出します。  
  
    -   タイプ ライブラリを含んでいる DLL の名前と場所  
  
    -   名前と名前空間の場所に情報を配置する必要があります。  
  
    -   ターゲットの相互運用機能アセンブリの名前と場所  
  
     次にコード例を示します。  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp を使用して、未登録の COM オブジェクトの場合でも、タイプ ライブラリの相互運用機能アセンブリを作成することができます。 ただし、使用されるコンピューターの相互運用機能アセンブリによって参照される COM オブジェクトを正しく登録する必要があります。 Windows オペレーティング システムに含まれている Regsvr32 ユーティリティを使用して、COM オブジェクトを登録できます。  
  
## <a name="see-also"></a>関連項目

- [COM 相互運用](../../../visual-basic/programming-guide/com-interop/index.md)  
- [Tlbimp.exe (タイプ ライブラリ インポーター)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
- [Tlbexp.exe (タイプ ライブラリ エクスポーター)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)  
- [チュートリアル : COM オブジェクトによる継承の実装](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
- [相互運用性のトラブルシューティング](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
- [Imports ステートメント (.NET 名前空間および型)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
