---
title: C# の新機能 - C# ガイド
description: C# 言語がどのように進化しているか
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 3fc42809943b10d09d59780576dd9768d9e16ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c"></a>C# の新機能 #

このページでは、C# 言語の各メジャー リリースの新機能に関するロードマップを示しています。 以下のリンクで、各リリースで追加された主な機能の詳細情報を確認できます。

> [!IMPORTANT]
> C# 言語のこれらの機能のいくつかは、*標準ライブラリ*の型とメソッドに依存します。 一例として、例外処理があります。 すべての `throw` ステートメントまたは式は、スローされたオブジェクトが <xref:System.Exception> から派生していることを確認するために、チェックされます。 同様に、すべての `catch` は、キャッチされた型が <xref:System.Exception> から派生していることを確認するために、チェックされます。 バージョンごとに新しい要件が追加されている場合があります。 古い環境で言語の最新機能を使用するには、特定のライブラリをインストールする必要がある場合があります。 これらの依存関係については、特定のバージョンごとに用意されたページに記載されています。 詳細については、この依存関係のバックグラウンドにある[言語とライブラリ間の関係](relationships-between-language-and-library.md)に関する記事をご覧ください。 


* [C# 7.2](csharp-7-2.md):
    - このページでは C# 言語の最新の機能について説明します。 C# 7.2 は現在 [Visual Studio 2017 バージョン 15.5](https://www.visualstudio.com/vs/whatsnew/) および [.NET Core 2.0 SDK](../../core/whats-new/index.md) で利用可能です。

* [C# 7.1](csharp-7-1.md):
    - このページでは、C# 7.1 の機能について説明します。 これらの機能は、[Visual Studio 2017 バージョン 15.3](https://www.visualstudio.com/vs/whatsnew/) および [.NET Core 2.0 SDK](../../core/whats-new/index.md) に追加されています。

* [C# 7.0](csharp-7.md):
    - このページでは、C# 7.0 で追加された機能について説明します。 これらの機能は [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) および [.NET Core 1.0](../../core/whats-new/index.md) 以降で追加されました。
     
* [C# 6](csharp-6.md):
    - このページでは、C# 6 で追加された機能について説明します。 これらの機能は、Windows 開発者は Visual Studio 2015 で利用でき、macOS および Linux で C# を使用する開発者は .NET Core 1.0 で利用できます。

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* [クロス プラットフォーム サポート](../../core/index.md):
    - C# は .NET Core のサポートにより、複数のプラットフォームで実行できます。 macOS や、Linux をサポートする多くのディストリビューションのいずれかで C# を使用する場合は、.NET Core の詳細を確認してください。

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a>以前のバージョン
次の一覧は、C# 言語と Visual Studio .NET の以前のバージョンで導入された主な機能を示しています。  
  
 * Visual Studio .NET 2013: 
     - このバージョンの Visual Studio には、バグの修正、パフォーマンスの向上、.NET コンパイラ プラットフォーム ("Roslyn") の Technology Preview (後の <!--Link to ../roslyn/index.md-->.NET コンパイラ プラットフォーム SDK) が含まれています。

 * C# 5、Visual Studio .NET 2012: 
     - `Async` / `await`、および[呼び出し元情報](../programming-guide/concepts/caller-information.md)属性。

 * C# 4、Visual Studio .NET 2010: 
     - `Dynamic`、[名前付き引数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)、省略可能なパラメーター、ジェネリックの[共変性および反変性](../programming-guide/concepts/covariance-contravariance/index.md)。

 * C# 3、Visual Studio .NET 2008: 
     - オブジェクト初期化子とコレクション初期化子、ラムダ式、拡張メソッド、匿名型、自動プロパティ、ローカル `var` 型推論、および[統合言語クエリ (LINQ)](../programming-guide/concepts/linq/index.md)。

 * C# 2、Visual Studio .NET 2005: 
     - 匿名メソッド、ジェネリック、null 許容型、反復子/yield、`static` クラス、デリゲートの共変性および反変性。

 * C# 1.1、Visual Studio .NET 2003: 
     - `#line` プラグマと xml ドキュメント コメント。

 * C# 1、Visual Studio .NET 2002: 
     - [C#](../csharp.md) の最初のリリース。   
