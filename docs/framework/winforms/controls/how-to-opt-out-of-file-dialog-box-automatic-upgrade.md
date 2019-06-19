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
ms.openlocfilehash: 0753873ac37f26d6503397290ef4603702737a86
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170616"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="7e12e-102">方法: ファイル関連のダイアログ ボックスの自動アップグレードを無効にする</span><span class="sxs-lookup"><span data-stu-id="7e12e-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="7e12e-103">ときに、<xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>クラスは、アプリケーションで使用されて、外観と動作は、アプリケーションがで実行されている Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7e12e-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="7e12e-104">.NET Framework 2.0 またはそれ以前に作成されたアプリケーションが表示される場合[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]、<xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>で自動的に表示される、[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]外観と動作します。</span><span class="sxs-lookup"><span data-stu-id="7e12e-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="7e12e-105">以降、.NET Framework 3.0 では、次のように表示する自動アップグレードから選択できます、<xref:System.Windows.Forms.OpenFileDialog>と<xref:System.Windows.Forms.SaveFileDialog>で、 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-スタイルの外観と動作します。</span><span class="sxs-lookup"><span data-stu-id="7e12e-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="7e12e-106">ファイル関連のダイアログ ボックスの自動アップグレードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="7e12e-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="7e12e-107">設定、<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>プロパティの<xref:System.Windows.Forms.OpenFileDialog>または<xref:System.Windows.Forms.SaveFileDialog>に`false` ダイアログ ボックスを表示する前にします。</span><span class="sxs-lookup"><span data-stu-id="7e12e-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e12e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e12e-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
