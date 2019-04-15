---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235626"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="92c82-101">終了時に WinRT ストリーム アダプターで FlushAsync が自動的に呼び出されなくなりました</span><span class="sxs-lookup"><span data-stu-id="92c82-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="92c82-102">説明</span><span class="sxs-lookup"><span data-stu-id="92c82-102">Details</span></span>|<span data-ttu-id="92c82-103">Windows ストア アプリの Windows ランタイム ストリーム アダプターで、Dispose メソッドから FlushAsync メソッドが呼び出されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="92c82-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="92c82-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="92c82-104">Suggestion</span></span>|<span data-ttu-id="92c82-105">この変更は透過的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="92c82-105">This change should be transparent.</span></span> <span data-ttu-id="92c82-106">開発者は次のようなコードを記述して以前の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="92c82-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="92c82-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="92c82-107">Scope</span></span>|<span data-ttu-id="92c82-108">透明</span><span class="sxs-lookup"><span data-stu-id="92c82-108">Transparent</span></span>|
|<span data-ttu-id="92c82-109">Version</span><span class="sxs-lookup"><span data-stu-id="92c82-109">Version</span></span>|<span data-ttu-id="92c82-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="92c82-110">4.5.1</span></span>|
|<span data-ttu-id="92c82-111">型</span><span class="sxs-lookup"><span data-stu-id="92c82-111">Type</span></span>|<span data-ttu-id="92c82-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="92c82-112">Runtime</span></span>|
