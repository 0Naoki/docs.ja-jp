---
title: s_isDebuggerCheckDisabledForTestPurposes フィールド
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ab71ab6aa2b0ed454b86388ba369204a2131cca5
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634428"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="ccc04-102">s_isDebuggerCheckDisabledForTestPurposes フィールド</span><span class="sxs-lookup"><span data-stu-id="ccc04-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="ccc04-103">このプライベート フィールドで、`System.Windows.Diagnostics.VisualDiagnostics`クラスは、アクティブなデバッガー、内部のチェックを実行するかどうかを判断する Visual Studio によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccc04-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="ccc04-104">構文</span><span class="sxs-lookup"><span data-stu-id="ccc04-104">Syntax</span></span>

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> <span data-ttu-id="ccc04-105">Api、`System.Windows.Diagnostics.VisualDiagnostics`クラスは、アプリケーションがデバッガーで実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccc04-105">APIs in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="ccc04-106">設定`s_isDebuggerCheckDisabledForTestPurposes`に`true`デバッガーの外部 Api にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ccc04-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>
>
> <span data-ttu-id="ccc04-107">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ccc04-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ccc04-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ccc04-108">Requirements</span></span>

<span data-ttu-id="ccc04-109">**名前空間:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="ccc04-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="ccc04-110">**アセンブリ:** PresentationCore (presentationcore.dll 内)</span><span class="sxs-lookup"><span data-stu-id="ccc04-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="ccc04-111">**.NET framework のバージョン:** 4.6 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="ccc04-111">**.NET Framework versions:** Available since 4.6.</span></span>