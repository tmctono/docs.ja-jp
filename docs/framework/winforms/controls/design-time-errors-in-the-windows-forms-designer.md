---
title: Windows フォーム デザイナーでのデザイン時エラー
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015970"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="fb6ba-102">Windows フォームデザイナーのデザイン時エラー</span><span class="sxs-lookup"><span data-stu-id="fb6ba-102">Design-time errors in the Windows Forms Designer</span></span>

<span data-ttu-id="fb6ba-103">このトピックでは、Windows フォームデザイナーの読み込みに失敗したときに Visual Studio に表示されるデザイン時エラー一覧の意味と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-103">This topic explains the meaning and use of the design-time error list that appears in Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="fb6ba-104">このエラー リストが表示された場合、デザイナーのバグであると解釈するのではなく、コード内のエラーを修正するための参考情報であると考えてください。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>

<span data-ttu-id="fb6ba-105">エラーに関する詳細情報と考えられる解決策が提示されるので、このエラー リストの基本を理解することによって、アプリケーションのデバッグに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>

## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="fb6ba-106">デザイン時エラー一覧のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb6ba-106">The design-time error list interface</span></span>

<span data-ttu-id="fb6ba-107">Windows フォームデザイナーの読み込みに失敗した場合は、デザイナーにエラー一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-107">If the Windows Forms Designer fails to load, an error list appears in the designer.</span></span> <span data-ttu-id="fb6ba-108">エラーは複数のカテゴリに分類されています。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-108">The errors are grouped into categories.</span></span> <span data-ttu-id="fb6ba-109">たとえば、宣言されていない変数の 4 つのインスタンスがある場合、それらは同じエラー カテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="fb6ba-110">各エラー カテゴリには、エラーの概要を示す簡単な説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-110">Each error category includes a brief description that summarizes the error.</span></span>

<span data-ttu-id="fb6ba-111">エラー カテゴリの見出しをクリックするか、展開/折りたたみシェブロンをクリックすることで、エラー カテゴリを展開したり、折りたたんだりできます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="fb6ba-112">エラー カテゴリを展開すると、次の追加のヘルプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-112">When you expand an error category, the following additional help is displayed:</span></span>

- <span data-ttu-id="fb6ba-113">このエラーのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-113">Instances of this error.</span></span>

- <span data-ttu-id="fb6ba-114">このエラーのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-114">Help with this error.</span></span>

- <span data-ttu-id="fb6ba-115">このエラーに関するフォーラムの投稿。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-115">Forum posts about this error.</span></span>

### <a name="instances-of-this-error"></a><span data-ttu-id="fb6ba-116">このエラーのインスタンス</span><span class="sxs-lookup"><span data-stu-id="fb6ba-116">Instances of this error</span></span>

<span data-ttu-id="fb6ba-117">追加のヘルプには、現在のプロジェクトにおけるエラーのすべてのインスタンスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="fb6ba-118">多くのエラーには、次の形式の正確な場所が含まれます: *[プロジェクト名]* *[フォーム名]* 行: *[行番号]* 列: *[列番号]* 。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="fb6ba-119">**[コードに移動]** リンクを使用して、エラーが発生したコード内の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>

<span data-ttu-id="fb6ba-120">呼び出し履歴がエラーに関連付けられている場合、 **[コール スタックの表示]** リンクをクリックすると、エラーがさらに展開され、呼び出し履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="fb6ba-121">履歴を調べると、有用なデバッグ情報を得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="fb6ba-122">たとえば、エラーが発生する前に呼び出された関数を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="fb6ba-123">呼び出し履歴を選択して、コピーおよび保存できます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-123">The call stack is selectable so that you can copy and save it.</span></span>

> [!NOTE]
> <span data-ttu-id="fb6ba-124">Visual Basic では、デザイン時エラー リストには複数のエラーは表示されませんが、同じエラーの複数のインスタンスが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="fb6ba-125">Visual C++ では、エラーに goto コード リンク/行番号リンクはありません。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>

### <a name="forum-posts-about-this-error"></a><span data-ttu-id="fb6ba-126">このエラーに関するフォーラムの投稿</span><span class="sxs-lookup"><span data-stu-id="fb6ba-126">Forum posts about this error</span></span>

<span data-ttu-id="fb6ba-127">追加のヘルプには、エラーに関連するフォーラムの投稿へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-127">The additional help includes a link to forum posts related to the error.</span></span> <span data-ttu-id="fb6ba-128">フォーラムは、エラー メッセージの文字列に基づいて検索されます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-128">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="fb6ba-129">次のフォーラムで検索を試すこともできます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-129">You can also try searching on the following forums:</span></span>

- [<span data-ttu-id="fb6ba-130">Windows フォームデザイナーフォーラム</span><span class="sxs-lookup"><span data-stu-id="fb6ba-130">Windows Forms Designer forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [<span data-ttu-id="fb6ba-131">Windows フォームフォーラム</span><span class="sxs-lookup"><span data-stu-id="fb6ba-131">Windows Forms forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a><span data-ttu-id="fb6ba-132">無視して続行</span><span class="sxs-lookup"><span data-stu-id="fb6ba-132">Ignore and continue</span></span>

<span data-ttu-id="fb6ba-133">エラー状態を無視して、デザイナーの読み込みを続行することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-133">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="fb6ba-134">この操作を選択すると、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-134">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="fb6ba-135">たとえば、デザイン サーフェイスにコントロールが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb6ba-135">For example, controls may not appear on the design surface.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb6ba-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb6ba-136">See also</span></span>

- <span data-ttu-id="fb6ba-137">[デザイン時開発のトラブルシューティング](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="fb6ba-137">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
- [<span data-ttu-id="fb6ba-138">コントロールとコンポーネントの作成時のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fb6ba-138">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)
- [<span data-ttu-id="fb6ba-139">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="fb6ba-139">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="fb6ba-140">[Windows フォーム デザイナーのエラー メッセージ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fb6ba-140">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span></span>
