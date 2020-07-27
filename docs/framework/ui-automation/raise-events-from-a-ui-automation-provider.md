---
title: UI オートメーション プロバイダーからのイベントの発生
description: UI オートメーションプロバイダーからイベントを発生させる方法を示す例を参照してください。 このメソッドは、カスタムボタンコントロールの実装で UI オートメーションイベントを発生させます。
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 75af4d05172e2417d44f76beab486de5eb3a4ba7
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168106"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="11d50-104">UI オートメーション プロバイダーからのイベントの発生</span><span class="sxs-lookup"><span data-stu-id="11d50-104">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="11d50-105">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="11d50-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="11d50-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11d50-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="11d50-107">このトピックには、UI オートメーション プロバイダーからイベントを発生させる方法を示すコード例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="11d50-107">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11d50-108">例</span><span class="sxs-lookup"><span data-stu-id="11d50-108">Example</span></span>  
 <span data-ttu-id="11d50-109">次の例では、カスタム ボタン コントロールの実装で [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="11d50-109">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="11d50-110">実装により、UI オートメーション クライアント アプリケーションがボタンのクリックをシミュレートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="11d50-110">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="11d50-111">不要な処理を回避するために、例では <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> をチェックして、イベントが発生するかどうかを確認しています。</span><span class="sxs-lookup"><span data-stu-id="11d50-111">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="11d50-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="11d50-112">See also</span></span>

- [<span data-ttu-id="11d50-113">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="11d50-113">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
