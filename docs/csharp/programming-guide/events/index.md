---
title: イベント - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 7a8a8e6b6a393f151d69d1879f475e04f44df5fa
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590383"
---
# <a name="events-c-programming-guide"></a>イベント (C# プログラミング ガイド)
[クラス](../../language-reference/keywords/class.md) やオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。 イベントを送信する ( *発生させる*) クラスを *パブリッシャー* 、イベントを受信する ( *処理する*) クラスを *サブスクライバー*と呼びます。  
  
 一般的な C# Windows フォームまたは Web アプリケーションでは、ボタンやリスト ボックスなどのコントロールによって発生したイベントを定期受信します。 Visual C# 統合開発環境 (IDE) を使用して、コントロールによって発行されるイベントを参照し、処理するイベントを選択できます。 IDE は、空のイベント ハンドラー メソッドとイベントを定期受信するためのコードを自動的に追加する方法を提供します。 詳細については、「[方法 :イベント サブスクリプションとサブスクリプションの解除](./how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。  
  
## <a name="events-overview"></a>イベントの概要  
 イベントには次のようなプロパティがあります。  
  
- パブリッシャーがイベントが発生するタイミングを判断し、サブスクライバーがイベントに対応して実行するアクションを決定します。  
  
- イベントには複数のサブスクライバーを指定できます。 サブスクライバーは、複数のパブリッシャーからの複数のイベントを処理できます。  
  
- サブスクライバーがないイベントは発生しません。  
  
- イベントは一般的に、グラフィカル ユーザー インターフェイスでのボタンのクリックやメニューの選択などのユーザーの操作を知らせるために使用されます。  
  
- イベントに複数のサブスクライバーがある場合は、イベントが発生したときに複数のイベント ハンドラーが同時に呼び出されます。 イベントを非同期に呼び出すには、[同期メソッドの非同期呼び出し](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)を参照してください。  
  
- .NET Framework クラス ライブラリ以内で、イベントは、<xref:System.EventHandler> デリゲートおよび <xref:System.EventArgs> 基底クラスを基にしています。  
  
## <a name="related-sections"></a>関連項目  
 詳細については次を参照してください:  
  
- [方法: イベント サブスクリプションとサブスクリプションの解除](./how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
- [方法: .NET Framework ガイドラインに準拠したイベントを発行する](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
- [方法: 派生クラスから基本クラス イベントを発生させる](./how-to-raise-base-class-events-in-derived-classes.md)  
  
- [方法: インターフェイス イベントを実装する](./how-to-implement-interface-events.md)  
  
- [方法: カスタム イベント アクセサーを実装する](./how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a>C# 言語仕様  

詳細については、「[C# 言語の仕様](../../language-reference/language-specification/index.md)」の「[イベント](~/_csharplang/spec/classes.md#events)」を参照してください。 言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。
  
## <a name="featured-book-chapters"></a>参考書籍の該当する章  
 「[Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)」(『[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers (C# 3.0 クックブック (第 3 版): C# 3.0 プログラマ向けの 250 以上のソリューション)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)』)  
  
 「[デリゲートとイベント](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29)」(『[Learning C# 3.0: Master the fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)』)  
  
## <a name="see-also"></a>関連項目

- <xref:System.EventHandler>
- [C# プログラミング ガイド](../index.md)
- [デリゲート](../delegates/index.md)
- [Windows フォーム内でのイベント ハンドラーの作成](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
