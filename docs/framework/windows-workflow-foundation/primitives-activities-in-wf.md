---
title: WF 内のプリミティブ アクティビティ
ms.date: 03/30/2017
ms.assetid: 8e9009d1-236e-4d8e-86fc-e43132bf6dfc
ms.openlocfilehash: d87125d8d85fa33a49651dfabb840881b0e216ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780706"
---
# <a name="primitives-activities-in-wf"></a><span data-ttu-id="05b46-102">WF 内のプリミティブ アクティビティ</span><span class="sxs-lookup"><span data-stu-id="05b46-102">Primitives Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="05b46-103">には、共通のタスクを実行する便利な機構を提供する、システムによって提供されるアクティビティがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="05b46-103">provides several system-provided activities that provide a convenient mechanism for performing common tasks.</span></span>  
  
|<span data-ttu-id="05b46-104">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="05b46-104">Activity</span></span>|<span data-ttu-id="05b46-105">説明</span><span class="sxs-lookup"><span data-stu-id="05b46-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Assign>|<span data-ttu-id="05b46-106">現在のスコープで、変数に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="05b46-106">Assigns a value to a variable at the current scope.</span></span>|  
|<xref:System.Activities.Statements.Delay>|<span data-ttu-id="05b46-107">1 つの実行パスをアイドル状態にして、場合によってはワークフローをアンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="05b46-107">Puts one path of execution into an idle state, possibly allowing the workflow to be unloaded.</span></span>|  
|<xref:System.Activities.Statements.InvokeDelegate>|<span data-ttu-id="05b46-108"><xref:System.Activities.ActivityDelegate> から派生し、プロパティとして公開されるデリゲートを実行します。</span><span class="sxs-lookup"><span data-stu-id="05b46-108">Executes a delegate that derives from <xref:System.Activities.ActivityDelegate> and is exposed as a property.</span></span>|  
|<xref:System.Activities.Statements.InvokeMethod>|<span data-ttu-id="05b46-109">CLR オブジェクトのパブリック メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="05b46-109">Executes a public method of a CLR object.</span></span>|  
|<xref:System.Activities.Statements.WriteLine>|<span data-ttu-id="05b46-110">指定した文字列を、コンソールまたは指定した <xref:System.IO.TextWriter> オブジェクトに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="05b46-110">Writes a specified string to the console or a specified <xref:System.IO.TextWriter> object.</span></span>|
