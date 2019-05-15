---
title: Windows フォームで ActiveX コントロールをホストする場合の考慮事項
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: 4b604502e0fea591460f30cae28b64ff1703da65
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589441"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="eb221-102">Windows フォームで ActiveX コントロールをホストする場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="eb221-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="eb221-103">Windows フォームは、Windows フォーム コントロールをホストするために最適化されていますが、ActiveX コントロールを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="eb221-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="eb221-104">ActiveX コントロールを使うアプリケーションを計画するときは、次の考慮事項に留意してください。</span><span class="sxs-lookup"><span data-stu-id="eb221-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
- <span data-ttu-id="eb221-105">**セキュリティ** 共通言語ランタイムは、コード アクセス セキュリティに関して強化されました。</span><span class="sxs-lookup"><span data-stu-id="eb221-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="eb221-106">Windows フォームを使うアプリケーションは、完全に信頼された環境では問題なく動作し、信頼性が高くない環境ではほとんどの機能がアクセス可能な状態で動作します。</span><span class="sxs-lookup"><span data-stu-id="eb221-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="eb221-107">Windows フォーム コントロールは、ブラウザーで問題なくホストできます。</span><span class="sxs-lookup"><span data-stu-id="eb221-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="eb221-108">ただし、Windows フォームの ActiveX コントロールは、これらのセキュリティ強化を利用できません。</span><span class="sxs-lookup"><span data-stu-id="eb221-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="eb221-109">ActiveX コントロールを実行するには、アンマネージ コード アクセス許可が設定されている必要があります、<xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eb221-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="eb221-110">セキュリティとアンマネージ コード アクセス許可の詳細については、次を参照してください。<xref:System.Security.Permissions.SecurityPermissionAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="eb221-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
- <span data-ttu-id="eb221-111">**総保有コスト** Windows フォームに追加される ActiveX コントロールは、その Windows フォーム全体と共に配置されるため、作成されるファイルのサイズが大幅に追加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb221-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="eb221-112">さらに、Windows フォームで ActiveX コントロールを使うには、レジストリへの書き込みが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb221-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="eb221-113">これは、レジストリへの書き込みを必要としない Windows フォーム コントロールと比較して、ユーザーのコンピューターに大きく干渉します。</span><span class="sxs-lookup"><span data-stu-id="eb221-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb221-114">ActiveX コントロールを操作するには、COM 相互運用ラッパーを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb221-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="eb221-115">詳しくは、「[Visual Basic および Visual C# における COM 相互運用性](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eb221-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb221-116">ActiveX コントロールのメンバーの名前が、.NET Framework で定義された名前と一致するかどうかは、ActiveX コントロール インポーターは、メンバー名をプレフィックス**Ctl**作成時、<xref:System.Windows.Forms.AxHost>クラスを派生します。</span><span class="sxs-lookup"><span data-stu-id="eb221-116">If the name of a member of the ActiveX control matches a name defined in the .NET Framework, then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="eb221-117">たとえば、ActiveX コントロールがあるという名前のメンバー**レイアウト**、名前が変更**CtlLayout** 、AxHost 派生クラスでため、**レイアウト**内でイベントが定義されている、します。NET Framework。</span><span class="sxs-lookup"><span data-stu-id="eb221-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb221-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb221-118">See also</span></span>

- [<span data-ttu-id="eb221-119">方法: Windows フォームに ActiveX コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb221-119">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="eb221-120">コード アクセス セキュリティ</span><span class="sxs-lookup"><span data-stu-id="eb221-120">Code Access Security</span></span>](../../misc/code-access-security.md)
- <span data-ttu-id="eb221-121">[各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb221-121">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="eb221-122">Windows フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="eb221-122">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="eb221-123">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="eb221-123">Windows Forms Controls</span></span>](index.md)
