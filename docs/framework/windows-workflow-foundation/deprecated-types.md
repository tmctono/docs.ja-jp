---
title: Windows Workflow Foundation で非推奨の型
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: c8325e60d708b53e1701a980355d5d2bf20e8a4b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644968"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="a54de-102">Windows Workflow Foundation で非推奨の型</span><span class="sxs-lookup"><span data-stu-id="a54de-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="a54de-103">.NET 4 の段階で、ワークフロー チームは、<xref:System.Activities> 名前空間のまったく新しいワークフロー エンジンをリリースしました。</span><span class="sxs-lookup"><span data-stu-id="a54de-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="a54de-104">ほとんどの"WF 3"で型をマークする .NET 4.5 ベータ版のリリースでは<xref:System.Workflow.Activities>、 <xref:System.Workflow.ComponentModel>、および<xref:System.Workflow.Runtime>不使用と名前空間。</span><span class="sxs-lookup"><span data-stu-id="a54de-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="a54de-105">旧式の名前空間とツール</span><span class="sxs-lookup"><span data-stu-id="a54de-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="a54de-106">次のアセンブリには、今後非推奨とされるパブリック型が 1 つ以上含まれています：</span><span class="sxs-lookup"><span data-stu-id="a54de-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
- <span data-ttu-id="a54de-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="a54de-107">System.Workflow.Activities.dll</span></span>  
  
- <span data-ttu-id="a54de-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="a54de-108">System.Workflow.ComponentModel.dll</span></span>  
  
- <span data-ttu-id="a54de-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="a54de-109">System.Workflow.Runtime.dll</span></span>  
  
- <span data-ttu-id="a54de-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="a54de-110">System.WorkflowServices.dll</span></span>  
  
- <span data-ttu-id="a54de-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="a54de-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
- <span data-ttu-id="a54de-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="a54de-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
- <span data-ttu-id="a54de-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="a54de-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="a54de-114">その結果、非推奨とされた WF 3 API を今後使用すると、ビルド時に警告が発生し、次のようなメッセージが表示されます：</span><span class="sxs-lookup"><span data-stu-id="a54de-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="a54de-115">**警告 bc 40000:X は廃止されています。WF 3 の型が非推奨とされます。代わりに WF 4 を使用してください。**</span><span class="sxs-lookup"><span data-stu-id="a54de-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="a54de-116">WF 3 の型は .NET Framework の将来のリリースで削除されますが、実際の削除時期はまだ未定です (4.5 では行われません)。</span><span class="sxs-lookup"><span data-stu-id="a54de-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="a54de-117">この段階的な変更は、今後の方向性を示し、お客様が WF 4 モデルに余裕をもって移行するための期間を確保するためのものです。</span><span class="sxs-lookup"><span data-stu-id="a54de-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="a54de-118">WF 3 の型をサポートするためにいく予定、もちろん、[マイクロソフト サポート ライフ サイクル ポリシー](https://aka.ms/MicrosoftSupportLifecycle)します。</span><span class="sxs-lookup"><span data-stu-id="a54de-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](https://aka.ms/MicrosoftSupportLifecycle).</span></span> <span data-ttu-id="a54de-119">既存の WF3 のアプリケーションでは、.NET 4.5 では、上で問題なく実行され、Visual Studio 2012 が新規および既存の wf 3 ベースのソリューションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a54de-119">Existing WF3 applications will run without issue on .NET 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="a54de-120"><xref:System.Workflow.Activities.Rules> 名前空間に含まれるルール関連の型については、WF 4.5 には相当する型がないため、非推奨扱いにはなりません。</span><span class="sxs-lookup"><span data-stu-id="a54de-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="a54de-121">WF 4 へのアプリケーション移行を希望お客様は、のヘルプを検索は、[ワークフロー 4 移行ガイダンス](migration-guidance.md)します。</span><span class="sxs-lookup"><span data-stu-id="a54de-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
