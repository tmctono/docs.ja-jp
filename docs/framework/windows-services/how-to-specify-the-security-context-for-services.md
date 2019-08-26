---
title: '方法: サービスのセキュリティ コンテキストを指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
ms.openlocfilehash: 88dc9c40a2b8ff0ac9bba26c991ba2a4ac2dcb43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952430"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="36d65-102">方法: サービスのセキュリティ コンテキストを指定する</span><span class="sxs-lookup"><span data-stu-id="36d65-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="36d65-103">既定では、サービスはログインしているユーザーのセキュリティ コンテキストとは異なるセキュリティ コンテキストで実行します。</span><span class="sxs-lookup"><span data-stu-id="36d65-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="36d65-104">サービスは `LocalSystem` という名前の既定のシステム アカウントのコンテキストで実行し、このコンテキストはサービスに対してユーザーとは異なるシステム リソースへのアクセス特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="36d65-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="36d65-105">この動作を変更し、サービスの実行が異なるユーザー アカウントで行われるように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="36d65-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="36d65-106">サービスが実行しているプロセスの <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> プロパティを操作することで、セキュリティ コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="36d65-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="36d65-107">このプロパティでは、次の 4 種類のアカウントのいずれかに、サービスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="36d65-107">This property allows you to set the service to one of four account types:</span></span>  
  
- <span data-ttu-id="36d65-108">`User`: システムは、サービスのインストール時に有効なユーザー名とパスワードの指定を要求し、ネットワーク上の 1 人のユーザーによって指定されたアカウントのコンテキストで実行します。</span><span class="sxs-lookup"><span data-stu-id="36d65-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
- <span data-ttu-id="36d65-109">`LocalService`: ローカル コンピューター上で非特権ユーザーとして機能し、リモート サーバーに匿名の資格情報を提示するアカウントのコンテキストで実行します。</span><span class="sxs-lookup"><span data-stu-id="36d65-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
- <span data-ttu-id="36d65-110">`LocalSystem`: 広範なローカル特権を提供し、リモート サーバーにコンピューターの資格情報を提示するアカウントのコンテキストで実行します。</span><span class="sxs-lookup"><span data-stu-id="36d65-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
- <span data-ttu-id="36d65-111">`NetworkService`: ローカル コンピューター上で非特権ユーザーとして機能し、リモート サーバーにコンピューターの資格情報を提示するアカウントのコンテキストで実行します。</span><span class="sxs-lookup"><span data-stu-id="36d65-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="36d65-112">詳細については、<xref:System.ServiceProcess.ServiceAccount> 列挙型のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36d65-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="36d65-113">サービスのセキュリティ コンテキストを指定するには</span><span class="sxs-lookup"><span data-stu-id="36d65-113">To specify the security context for a service</span></span>  
  
1. <span data-ttu-id="36d65-114">サービスの作成後、必要なインストーラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="36d65-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="36d65-115">詳細については、「[方法 :サービス アプリケーションにインストーラーを追加する](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36d65-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2. <span data-ttu-id="36d65-116">デザイナーで、`ProjectInstaller` クラスにアクセスし、対象となるサービスのサービス プロセス インストーラーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36d65-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="36d65-117">すべてのサービス アプリケーションについて、`ProjectInstaller` クラスには少なくとも 2 つのインストール コンポーネントがあります。プロジェクト内のすべてのサービスに対するプロセスをインストールするものと、アプリケーションに含まれるサービスごとに 1 つのインストーラーです。</span><span class="sxs-lookup"><span data-stu-id="36d65-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="36d65-118">このインスタンスでは、<xref:System.ServiceProcess.ServiceProcessInstaller> を選びます。</span><span class="sxs-lookup"><span data-stu-id="36d65-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3. <span data-ttu-id="36d65-119">**[プロパティ]** ウィンドウで、<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="36d65-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d65-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="36d65-120">See also</span></span>

- [<span data-ttu-id="36d65-121">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="36d65-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="36d65-122">方法: サービス アプリケーションにインストーラーを追加する</span><span class="sxs-lookup"><span data-stu-id="36d65-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="36d65-123">方法: Windows サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="36d65-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
