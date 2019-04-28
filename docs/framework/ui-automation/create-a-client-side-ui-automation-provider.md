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
ms.openlocfilehash: 03f64386271565b3494b9dac42cf969fc777e40b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61610030"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="a7ed7-102">クライアント側 UI オートメーション プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="a7ed7-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="a7ed7-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a7ed7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a7ed7-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="a7ed7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a7ed7-105">このトピックのコード例では、クライアント側 UI オートメーション プロバイダーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a7ed7-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ed7-106">例</span><span class="sxs-lookup"><span data-stu-id="a7ed7-106">Example</span></span>  
 <span data-ttu-id="a7ed7-107">コンソール ウィンドウの非常に単純なクライアント側プロバイダーを実装する [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] に、次のコード例を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a7ed7-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="a7ed7-108">このコードは、有用な機能は備えていませんが、UI オートメーション クライアント アプリケーションによって登録できるプロバイダー アセンブリを設定する際の基本的な手順を示すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="a7ed7-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="a7ed7-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7ed7-109">See also</span></span>

- [<span data-ttu-id="a7ed7-110">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="a7ed7-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="a7ed7-111">クライアント側プロバイダー アセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="a7ed7-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
