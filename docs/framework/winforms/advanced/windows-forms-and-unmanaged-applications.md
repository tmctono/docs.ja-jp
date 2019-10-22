---
title: Windows フォームとアンマネージド アプリケーション
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 65465f22b1806d385523c894cce2103afe33c2f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746728"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="d0c1c-102">Windows フォームとアンマネージド アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d0c1c-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="d0c1c-103">Windows フォーム アプリケーションとコントロールは、いくつかの注意事項がありますが、アンマネージ アプリケーションと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="d0c1c-104">次のセクションでは、Windows フォーム アプリケーションとコントロールがサポートするシナリオと構成、および、サポートしないシナリオと構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0c1c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d0c1c-105">In This Section</span></span>  
 [<span data-ttu-id="d0c1c-106">Windows フォームおよびアンマネージ アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="d0c1c-106">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="d0c1c-107">アンマネージ アプリケーションで使用する Windows フォーム コントロールを実装する方法に関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="d0c1c-108">方法: ShowDialog メソッドを使用して Windows フォームを表示して COM 相互運用機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="d0c1c-109"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用して Windows フォームをアンマネージ アプリケーションで実行する方法を示すコード例を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="d0c1c-110">方法: 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="d0c1c-111">独自のスレッドで Windows フォームを実行する方法を示すコード例を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="d0c1c-112">参照してください[チュートリアル。独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートしている](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d0c1c-113">参照</span><span class="sxs-lookup"><span data-stu-id="d0c1c-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d0c1c-114">Windows フォーム用の個別のスレッドの作成に使用します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d0c1c-115">スレッドのメッセージ ループを開始します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="d0c1c-116">フォームにアンマネージ アプリケーションからの呼び出しをマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d0c1c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0c1c-117">Related Sections</span></span>  
 [<span data-ttu-id="d0c1c-118">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="d0c1c-118">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="d0c1c-119">.NET Framework の型をアンマネージ アプリケーションで使用する方法に関する一般情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0c1c-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
