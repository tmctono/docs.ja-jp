---
title: UI オートメーション プロバイダーからのプロパティの返却
description: UI オートメーションプロバイダーが要素のプロパティを .NET のクライアントアプリケーションに返す方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 14a42c73d1dfb942a7e60ce7a72c3a5aea2b820c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903845"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="b616c-103">UI オートメーション プロバイダーからのプロパティの返却</span><span class="sxs-lookup"><span data-stu-id="b616c-103">Return Properties from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="b616c-104">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b616c-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b616c-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b616c-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b616c-106">このトピックのサンプル コードでは、UI オートメーション プロバイダーが、要素のプロパティをクライアント アプリケーションへどのように返すかを示します。</span><span class="sxs-lookup"><span data-stu-id="b616c-106">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="b616c-107">明示的にサポートしていないプロパティについては、プロバイダーは `null` (Visual Basic では`Nothing` ) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b616c-107">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="b616c-108">これにより、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] はホスト ウィンドウ プロバイダーなど、別のソースからプロパティを取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="b616c-108">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b616c-109">例</span><span class="sxs-lookup"><span data-stu-id="b616c-109">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="b616c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b616c-110">See also</span></span>

- [<span data-ttu-id="b616c-111">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="b616c-111">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="b616c-112">サーバー側 UI オートメーション プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="b616c-112">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
