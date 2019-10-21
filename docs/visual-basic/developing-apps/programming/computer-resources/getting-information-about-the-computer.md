---
title: '方法: コンピューターについての情報の取得 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Info object [Visual Basic], tasks
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
ms.openlocfilehash: c313f96ec17e2cfb1d94fedebbce5b2f5b8dbc95
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581257"
---
# <a name="getting-information-about-the-computer-visual-basic"></a><span data-ttu-id="d6144-102">方法: コンピューターについての情報の取得 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6144-102">Getting Information about the Computer (Visual Basic)</span></span>

<span data-ttu-id="d6144-103">`My.Computer.Info` オブジェクトは、コンピューターのメモリ、読み込まれたアセンブリ名、オペレーティング システムに関する情報を取得するためのプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="d6144-103">The `My.Computer.Info` object provides properties for getting information about the computer's memory, loaded assemblies, name, and operating system.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6144-104">解説</span><span class="sxs-lookup"><span data-stu-id="d6144-104">Remarks</span></span>

<span data-ttu-id="d6144-105">この表は `My.Computer.Info` オブジェクトでよく処理されるタスクを一覧にしたものであり、各タスクの実行方法を実演するトピックにここからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d6144-105">This table lists tasks commonly accomplished through the `My.Computer.Info` object and points to topics demonstrating how to perform each.</span></span>

|<span data-ttu-id="d6144-106">終了</span><span class="sxs-lookup"><span data-stu-id="d6144-106">To</span></span>|<span data-ttu-id="d6144-107">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="d6144-107">See</span></span>|
|---|---|
|<span data-ttu-id="d6144-108">アプリケーションがインストールされているコンピューターで使用できる仮想アドレス領域の量を確認する</span><span class="sxs-lookup"><span data-stu-id="d6144-108">Determine how much virtual address space is available for the computer on which the application is installed</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|
|<span data-ttu-id="d6144-109">アプリケーションを実行しているコンピューターのプラットフォームの種類を確認する</span><span class="sxs-lookup"><span data-stu-id="d6144-109">Determine the platform type of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|
|<span data-ttu-id="d6144-110">アプリケーションを実行しているコンピューターのオペレーティング システムの種類を確認する</span><span class="sxs-lookup"><span data-stu-id="d6144-110">Determine the operating system of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|
|<span data-ttu-id="d6144-111">アプリケーションを実行しているコンピューターにインストールされているサービス パックを確認する</span><span class="sxs-lookup"><span data-stu-id="d6144-111">Determine what service packs have been installed on the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|
|<span data-ttu-id="d6144-112">アプリケーションを実行しているコンピューターにインストールされている `UICulture` を確認する</span><span class="sxs-lookup"><span data-stu-id="d6144-112">Determine the installed `UICulture` on the computer on which the application is running.</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|

## <a name="see-also"></a><span data-ttu-id="d6144-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6144-113">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
