---
title: マネージド HTML DOM (Document Object Model) の非公開メンバーへのアクセス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 539ac998a557615c097c33cdd4207e99f396e81d
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959620"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="afdde-102">マネージド HTML DOM (Document Object Model) の非公開メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="afdde-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="afdde-103">マネージ HTML ドキュメント オブジェクト モデル (DOM) と呼ばれるクラスが含まれています<xref:System.Windows.Forms.HtmlElement>プロパティ、メソッド、およびすべての HTML 要素が共通のイベントを公開します。</span><span class="sxs-lookup"><span data-stu-id="afdde-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="afdde-104">場合によっては、ただし、必要があります、マネージ インターフェイスを直接公開しないメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="afdde-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="afdde-105">このトピックでは、Web ページ内で定義されている JScript および VBScript の関数を含む、非公開のメンバーにアクセスするための 2 つの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afdde-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="afdde-106">管理インターフェイスを介して非公開メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="afdde-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="afdde-107"><xref:System.Windows.Forms.HtmlDocument> <xref:System.Windows.Forms.HtmlElement>非公開メンバーへのアクセスを有効にする 4 つのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="afdde-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="afdde-108">次の表は、種類とその対応するメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="afdde-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="afdde-109">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="afdde-109">Member Type</span></span>|<span data-ttu-id="afdde-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="afdde-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="afdde-111">プロパティ (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="afdde-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="afdde-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="afdde-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="afdde-113">イベント (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="afdde-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="afdde-114">イベント (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="afdde-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="afdde-115">イベント (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="afdde-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="afdde-116">これらのメソッドを使用すると、適切な基になる型の要素があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="afdde-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="afdde-117">リッスンするようにするとします、`Submit`のイベントを`FORM`HTML 要素をページにいくつかの事前処理を実行できるように、`FORM`の値は、ユーザーがそれらをサーバーに送信する前にします。</span><span class="sxs-lookup"><span data-stu-id="afdde-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="afdde-118">理想的には、定義、HTML を制御する場合は、`FORM`を一意に`ID`属性。</span><span class="sxs-lookup"><span data-stu-id="afdde-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="afdde-119">このページの読み込み後、<xref:System.Windows.Forms.WebBrowser>コントロールを使用できます、<xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>を取得するメソッド、`FORM`を使用して実行時に`form1`引数として。</span><span class="sxs-lookup"><span data-stu-id="afdde-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="afdde-120">アンマネージ インターフェイスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="afdde-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="afdde-121">各 DOM クラスによって公開されているアンマネージ コンポーネント オブジェクト モデル (COM) インターフェイスを使用してマネージ HTML DOM の非公開メンバーにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="afdde-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="afdde-122">非公開メンバーに対して複数の呼び出しを行う必要がある場合、または非公開メンバーがマネージ HTML DOM によってラップされていないその他のアンマネージ インターフェイスを返す場合、これは推奨します。</span><span class="sxs-lookup"><span data-stu-id="afdde-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="afdde-123">次の表ではすべてのマネージ HTML DOM を通じて公開されるアンマネージ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afdde-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="afdde-124">使用状況とコード例については、各リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="afdde-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="afdde-125">型</span><span class="sxs-lookup"><span data-stu-id="afdde-125">Type</span></span>|<span data-ttu-id="afdde-126">アンマネージ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afdde-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="afdde-127">これはサポートされていませんが、アプリケーションから HTML DOM のアンマネージ ライブラリ (MSHTML.dll) への参照を追加する COM インターフェイスを使用する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="afdde-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="afdde-128">詳細については、次を参照してください。[サポート技術情報記事 934368](https://support.microsoft.com/kb/934368)します。</span><span class="sxs-lookup"><span data-stu-id="afdde-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="afdde-129">スクリプト関数へのアクセス</span><span class="sxs-lookup"><span data-stu-id="afdde-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="afdde-130">HTML ページでは、JScript や VBScript などのスクリプト言語を使用して、1 つまたは複数の関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="afdde-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="afdde-131">これらの関数がの内側に配置する`SCRIPT` ページで、ページし、DOM のイベントに応答またはオンデマンドで実行できます</span><span class="sxs-lookup"><span data-stu-id="afdde-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="afdde-132">使用して HTML ページで定義する、スクリプト関数を呼び出すことができます、<xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="afdde-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="afdde-133">この返される結果に変換するキャストを使用するには、スクリプト メソッドは HTML 要素を返す場合、<xref:System.Windows.Forms.HtmlElement>します。</span><span class="sxs-lookup"><span data-stu-id="afdde-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="afdde-134">詳細とコード例では、次を参照してください。<xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>します。</span><span class="sxs-lookup"><span data-stu-id="afdde-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdde-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="afdde-135">See also</span></span>

- [<span data-ttu-id="afdde-136">マネージド HTML DOM (Document Object Model) の使用</span><span class="sxs-lookup"><span data-stu-id="afdde-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
