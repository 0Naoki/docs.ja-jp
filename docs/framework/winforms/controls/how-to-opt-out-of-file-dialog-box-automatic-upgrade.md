---
title: '方法: ファイル関連のダイアログ ボックスの自動アップグレードを無効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 6fd34e1127747739423f6402f128194a3a39f5e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089148"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="538ac-102">方法: ファイル関連のダイアログ ボックスの自動アップグレードを無効にする</span><span class="sxs-lookup"><span data-stu-id="538ac-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="538ac-103">ときに、<xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>クラスは、アプリケーションで使用されて、外観と動作は、アプリケーションがで実行されている Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="538ac-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="538ac-104">アプリケーションが作成されているときに、[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]に表示される前または[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]、<xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>で自動的に表示される、[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]外観と動作します。</span><span class="sxs-lookup"><span data-stu-id="538ac-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="538ac-105">以降では、 [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)]、表示する自動アップグレードをオプトアウトすることができます、<xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>で、 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-スタイルの外観と動作します。</span><span class="sxs-lookup"><span data-stu-id="538ac-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="538ac-106">ファイル関連のダイアログ ボックスの自動アップグレードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="538ac-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="538ac-107">設定、<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>プロパティの<xref:System.Windows.Forms.OpenFileDialog>または<xref:System.Windows.Forms.SaveFileDialog>に`false` ダイアログ ボックスを表示する前にします。</span><span class="sxs-lookup"><span data-stu-id="538ac-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538ac-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="538ac-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
