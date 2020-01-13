---
title: .NET Framework の配置
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
ms.openlocfilehash: cc4f9c38138a37b6068d33ffa4229a955db08c07
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716548"
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="7f1f5-102">.NET Framework の配置</span><span class="sxs-lookup"><span data-stu-id="7f1f5-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="7f1f5-103">.NET Framework ドキュメントのこのセクションでは、アプリケーションとともに .NET Framework をインストールする開発者、およびネットワーク上で .NET Framework を展開する管理者に対して情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="7f1f5-104">また、アクティベーション、配置に伴う再起動の問題、.NET Framework のインストールの進捗を監視する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f1f5-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7f1f5-105">In This Section</span></span>  
 [<span data-ttu-id="7f1f5-106">配置ガイド (開発者向け)</span><span class="sxs-lookup"><span data-stu-id="7f1f5-106">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)  
 <span data-ttu-id="7f1f5-107">開発者による .NET Framework とアプリケーションのユーザーのコンピューターへのインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="7f1f5-108">配置ガイド (管理者向け)</span><span class="sxs-lookup"><span data-stu-id="7f1f5-108">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)  
 <span data-ttu-id="7f1f5-109">システム管理者が、Microsoft Endpoint Configuration Manager を使用して、ネットワーク全体に .NET Framework とその依存関係を配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>  
  
 [<span data-ttu-id="7f1f5-110">.NET Framework 4.5 のインストール中のシステム再起動の削減</span><span class="sxs-lookup"><span data-stu-id="7f1f5-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)  
 <span data-ttu-id="7f1f5-111">再起動をできる限り回避する再起動マネージャーと、.NET Framework をインストールするアプリケーションがそれをどのように利用できるかを説明しています。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="7f1f5-112">方法: .NET Framework 4.5 インストーラーの進行状況を表示する</span><span class="sxs-lookup"><span data-stu-id="7f1f5-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="7f1f5-113">進行状況のビューを独自に表示する一方で、.NET Framework セットアップ プロセスをサイレントで起動および追跡する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="7f1f5-114">.NET Framework の初期化エラー: ユーザー エクスペリエンスの管理</span><span class="sxs-lookup"><span data-stu-id="7f1f5-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="7f1f5-115">ユーザーのコンピューターで無効な、またはインストールされていない CLR バージョンが .NET Framework アプリケーションで必要になると何が起きるか、そしてこのようなエラーの解決方法と、ユーザーに表示されるエラー メッセージの制御方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="7f1f5-116">方法: CLR のアクティブ化に関する問題をデバッグする</span><span class="sxs-lookup"><span data-stu-id="7f1f5-116">How to: Debug CLR Activation Issues</span></span>](how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="7f1f5-117">正しいバージョンの CLR でアプリケーションを実行して発生した問題を解決するために、どのようにして CLR アクティベーション ログを表示し、デバッグするかを説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1f5-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1f5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f1f5-118">See also</span></span>

- [<span data-ttu-id="7f1f5-119">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="7f1f5-119">Development Guide</span></span>](../development-guide.md)
