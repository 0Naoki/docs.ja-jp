---
title: '方法: プラットフォーム呼び出しを使用して Wave ファイルを再生する (C# プログラミング ガイド)'
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 6b20877e54722b338c9905445a39c42350c7f7d7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384870"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>方法: プラットフォーム呼び出しを使用して Wave ファイルを再生する (C# プログラミング ガイド)
以下の C# コードの例では、プラットフォーム呼び出しサービスを使用して、Windows オペレーティング システム上の .wav サウンド ファイルを再生する方法を示します。  
  
## <a name="example"></a>例  
 このコード例では、`DllImport` を使って `winmm.dll` の `PlaySound` メソッドのエントリ ポイントを `Form1 PlaySound()` としてインポートしています。 この例には、ボタンを含む簡単な Windows フォームがあります。 ボタンをクリックすると、Windows 標準の <xref:System.Windows.Forms.OpenFileDialog> ダイアログ ボックスが開き、再生するファイルを開くことができます。 Wave ファイルを選ぶと、そのファイルが `winmm.dll` ライブラリの `PlaySound()` メソッドによって再生されます。 このメソッドの詳細については、「[Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files)」(Waveform-Audio ファイルで PlaySound 関数を使用する) をご覧ください。 .wav 拡張子を持つファイルを参照して選び、**[開く]** をクリックすることで、プラットフォーム呼び出しを使って Wave ファイルを再生します。 テキスト ボックスに、選んだファイルの完全なパスが表示されます。  
  
 **[ファイルを開く]** ダイアログ ボックスは、次のフィルター設定によって拡張子 .wav を持つファイルのみを表示するようにフィルター処理されます。  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
### <a name="to-compile-the-code"></a>コードをコンパイルするには、次のようにします。  
  
1.  Visual Studio で新しい C# Windows アプリケーション プロジェクトを作成し、**WinSound** という名前にします。  
  
2.  上記のコードをコピーし、`Form1.cs` ファイルに貼り付けて内容を上書きします。  
  
3.  次のコードをコピーし、`Form1.Designer.cs` ファイルのすべての既存コードの後の `InitializeComponent()` メソッドに貼り付けます。  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  コードをコンパイルして実行します。  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 詳細については、「[.NET でのセキュリティ](../../../standard/security/index.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
 [相互運用性の概要](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [プラットフォーム呼び出しの詳細](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
 [プラットフォーム呼び出しによるデータのマーシャリング](../../../framework/interop/marshaling-data-with-platform-invoke.md)
