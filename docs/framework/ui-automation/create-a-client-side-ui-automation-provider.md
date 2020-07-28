---
title: クライアント側 UI オートメーション プロバイダーの作成
description: クライアント側 UI オートメーションプロバイダーを作成する方法の例を表示します。 この例では、コンソールウィンドウ用の単純なクライアント側プロバイダーを実装しています。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: a25966d0f11e409bd4e53f944fc2528360327039
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168468"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="9981f-104">クライアント側 UI オートメーション プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="9981f-104">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="9981f-105">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="9981f-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9981f-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9981f-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="9981f-107">このトピックのコード例では、クライアント側 UI オートメーション プロバイダーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9981f-107">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9981f-108">例</span><span class="sxs-lookup"><span data-stu-id="9981f-108">Example</span></span>  
 <span data-ttu-id="9981f-109">次のコード例は、コンソールウィンドウの非常に単純なクライアント側プロバイダーを実装するダイナミックリンクライブラリ (DLL) に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9981f-109">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="9981f-110">このコードは、有用な機能は備えていませんが、UI オートメーション クライアント アプリケーションによって登録できるプロバイダー アセンブリを設定する際の基本的な手順を示すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="9981f-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="9981f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9981f-111">See also</span></span>

- [<span data-ttu-id="9981f-112">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="9981f-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="9981f-113">クライアント側プロバイダー アセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="9981f-113">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
