---
title: DLL 内の関数の識別
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc160678817266dc649f60dc3f2cc77044c05691
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="identifying-functions-in-dlls"></a>DLL 内の関数の識別
DLL 関数の ID は、次の要素で構成されます。  
  
-   関数の名前または序数  
  
-   実装が含まれている DLL ファイルの名前  
  
 たとえば、User32.dll で **MessageBox** 関数を指定すると、関数 (**MessageBox**) とその場所 (User32.dll、User32、または user32) が識別されます。 Microsoft Windows のアプリケーション プログラミング インターフェイス (Win32 API) は、文字と文字列を処理する各関数の 2 つのバージョンを含めることができます。これは、1 バイト文字 ANSI バージョンと 2 バイト文字 Unicode バージョンです。 指定されていない場合、<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> フィールドによって表される文字セットは、既定で ANSI になります。 一部の関数は、2 つのより多くのバージョンを持つことができます。  
  
 **MessageBoxA** は、**MessageBox** 関数の ANSI のエントリ ポイントであり、**MessageBoxW** は Unicode バージョンです。 さまざまなコマンド ライン ツールを実行して、User32.dll などの特定の DLL の関数名の一覧を表示することができます。 たとえば、`dumpbin /exports user32.dll` または `link /dump /exports user32.dll` を使用して関数名を取得できます。  
  
 DLL で新しい名前を元のエントリ ポイントにマップする限り、コード内でアンマネージ関数の名前を自由に変更することができます。 マネージ ソース コードでアンマネージ DLL 関数の名前を変更する方法の詳細については、「[Specifying an Entry Point](../../../docs/framework/interop/specifying-an-entry-point.md)」(エントリ ポイントの指定) を参照してください。  
  
 プラットフォーム呼び出しにより、Win32 API とその他の DLL で関数を呼び出すことによって、オペレーティング システムの重要な部分を制御できます。 Win32 API に加えて、その他の多数の API と DLL を、プラットフォーム呼び出しによって使用できます。  
  
 次の表では、Win32 API のいくつかの一般的に使用される DLL について説明します。  
  
|[DLL]|コンテンツの説明|  
|---------|-----------------------------|  
|GDI32.dll|描画とフォントの管理などのデバイスの出力のグラフィックス デバイス インターフェイス (GDI) 関数。|  
|Kernel32.dll|メモリ管理とリソースの処理のための低レベルのオペレーティング システム関数。|  
|User32.dll|メッセージの処理、タイマー、メニュー、通信用の Windows 管理関数。|  
  
 Win32 API の詳細については、プラットフォーム SDK を参照してください。 プラットフォーム呼び出しで使用する .NET ベースの宣言を作成する方法を示す例については、「[プラットフォーム呼び出しによるデータのマーシャリング](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [アンマネージ DLL 関数の処理](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [エントリ ポイントの指定](../../../docs/framework/interop/specifying-an-entry-point.md)  
 [DLL 関数を保持するクラスの作成](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)  
 [マネージ コードでのプロトタイプの作成](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [DLL 関数の呼び出し](../../../docs/framework/interop/calling-a-dll-function.md)
