---
title: '方法: インストールされている WPF のバージョンを確認する'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768021"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="0c571-102">方法: インストールされている WPF のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="0c571-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="0c571-103">現在インストールされているバージョンのバージョン番号[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]にある、**レジストリ**します。</span><span class="sxs-lookup"><span data-stu-id="0c571-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="0c571-104">バージョン番号を検索するには。</span><span class="sxs-lookup"><span data-stu-id="0c571-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="0c571-105">**[スタート]** メニューで、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c571-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="0c571-106">**オープン**、型**regedit.exe**します。</span><span class="sxs-lookup"><span data-stu-id="0c571-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="0c571-107">次のキーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c571-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="0c571-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]にバージョン番号が格納されている、**バージョン**値。</span><span class="sxs-lookup"><span data-stu-id="0c571-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
