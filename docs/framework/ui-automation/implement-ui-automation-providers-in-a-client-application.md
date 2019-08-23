---
title: クライアント アプリケーションに UI オートメーション プロバイダーを実装する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: ef3d03bee412b97ed88ec76e81ad2fd19a9595eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968947"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="ea008-102">クライアント アプリケーションに UI オートメーション プロバイダーを実装する</span><span class="sxs-lookup"><span data-stu-id="ea008-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
> <span data-ttu-id="ea008-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="ea008-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ea008-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="ea008-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ea008-105">このトピックのコード例では、アプリケーション内のクライアント側 UI オートメーション プロバイダーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ea008-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="ea008-106">これは、一般的ではないシナリオです。</span><span class="sxs-lookup"><span data-stu-id="ea008-106">This is an uncommon scenario.</span></span> <span data-ttu-id="ea008-107">通常は、UI オートメーション クライアント アプリケーションは、サーバー側プロバイダーを使用するか、または DLL 内に存在するクライアント側プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea008-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea008-108">例</span><span class="sxs-lookup"><span data-stu-id="ea008-108">Example</span></span>  
 <span data-ttu-id="ea008-109">次のコード例では、コンソール ウィンドウ用の簡単なプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="ea008-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="ea008-110">このコードは、有用な機能は備えていませんが、クライアント コード内でプロバイダーを設定し、 <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>を使用して登録する際の基本的な手順を示すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea008-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="ea008-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea008-111">See also</span></span>

- [<span data-ttu-id="ea008-112">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="ea008-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="ea008-113">クライアント側プロバイダー アセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="ea008-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="ea008-114">クライアント側 UI オートメーション プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="ea008-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="ea008-115">クライアント側 UI オートメーション プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="ea008-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
