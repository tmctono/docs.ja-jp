---
title: クライアント側 UI オートメーション プロバイダーの作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: 722b6db8a777f0e945b91fa7fa27db0dd2858d7b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629535"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="a6ca2-102">クライアント側 UI オートメーション プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="a6ca2-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="a6ca2-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a6ca2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a6ca2-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="a6ca2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a6ca2-105">このトピックのコード例では、クライアント側 UI オートメーション プロバイダーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ca2-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ca2-106">例</span><span class="sxs-lookup"><span data-stu-id="a6ca2-106">Example</span></span>  
 <span data-ttu-id="a6ca2-107">次のコード例は、コンソールウィンドウの非常に単純なクライアント側プロバイダーを実装するダイナミックリンクライブラリ (DLL) に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a6ca2-107">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="a6ca2-108">このコードは、有用な機能は備えていませんが、UI オートメーション クライアント アプリケーションによって登録できるプロバイダー アセンブリを設定する際の基本的な手順を示すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6ca2-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="a6ca2-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6ca2-109">See also</span></span>

- [<span data-ttu-id="a6ca2-110">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="a6ca2-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="a6ca2-111">クライアント側プロバイダー アセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="a6ca2-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
