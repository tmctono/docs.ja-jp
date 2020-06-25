---
title: コントロール
description: Windows フォームコントロールを追加して配置する方法について説明します。 また、デザイナーでコントロールを操作し、実行時にコントロールを動的に追加するコードを記述することもできます。
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls
- controls [Windows Forms]
- Windows Forms controls, about Windows Forms controls
ms.assetid: f050de8f-4ebd-4042-94b8-edf9a1dbd52a
ms.openlocfilehash: 9ca4a2a1205663ae0ff4537a58cc1991a15da5d8
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324037"
---
# <a name="windows-forms-controls"></a><span data-ttu-id="c9a11-104">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="c9a11-104">Windows Forms controls</span></span>

<span data-ttu-id="c9a11-105">Windows フォーム アプリケーションのユーザー インターフェイスを設計および変更するときは、コントロールを追加、整列、配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9a11-105">As you design and modify the user interface of your Windows Forms applications, you will need to add, align, and position controls.</span></span> <span data-ttu-id="c9a11-106">コントロールは、フォーム オブジェクトに含まれるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c9a11-106">Controls are objects that are contained within form objects.</span></span> <span data-ttu-id="c9a11-107">コントロールの各種類には、そのコントロールを特定の目的に適したものにする固有のプロパティ、メソッド、イベントのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="c9a11-107">Each type of control has its own set of properties, methods, and events that make it suitable for a particular purpose.</span></span> <span data-ttu-id="c9a11-108">デザイナーでコントロールを操作し、実行時にコントロールを動的に追加するコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="c9a11-108">You can manipulate controls in the designer and write code to add controls dynamically at run time.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c9a11-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9a11-109">In this section</span></span>

<span data-ttu-id="c9a11-110">[Windows フォームにコントロールを配置する](putting-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-110">[Putting Controls on Windows Forms](putting-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="c9a11-111">フォームへのコントロールの追加に関連するリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9a11-111">Provides links related to putting controls on forms.</span></span>

<span data-ttu-id="c9a11-112">[Windows フォーム上のコントロールの配置](how-to-align-multiple-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-112">[Arranging Controls on Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="c9a11-113">フォーム上のコントロールの配置に関連する記事。</span><span class="sxs-lookup"><span data-stu-id="c9a11-113">Articles related to arranging controls on forms.</span></span>

<span data-ttu-id="c9a11-114">[個々の Windows フォームコントロールのラベル付けとそれらへのショートカットの提供](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-114">[Labeling Individual Windows Forms Controls and Providing Shortcuts to Them](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span></span>\
<span data-ttu-id="c9a11-115">キーボード ショートカット、コントロールのテキスト ラベル、修飾キーの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9a11-115">Describes the uses of keyboard shortcuts, text labels on controls, and modifier keys.</span></span>

<span data-ttu-id="c9a11-116">[Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-116">[Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md)</span></span>\
<span data-ttu-id="c9a11-117">Windows フォームで使うことができるコントロールの一覧、および各コントロールで実行できる基本的な事柄を示します。</span><span class="sxs-lookup"><span data-stu-id="c9a11-117">Lists the controls that work with Windows Forms, and basic things you can accomplish with each control.</span></span>

<span data-ttu-id="c9a11-118">[.NET Framework を使用したカスタム Windows フォームコントロールの開発](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-118">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="c9a11-119">カスタム Windows フォーム コントロールの開発に役立つ背景情報とサンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9a11-119">Provides background information and samples to help users develop custom Windows Forms controls.</span></span>

<span data-ttu-id="c9a11-120">[デザイン時の Windows フォームコントロールの開発](developing-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-120">[Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="c9a11-121">デザインと継承を使ってカスタム コントロールを作成するための手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9a11-121">Describes techniques for creating custom controls through design and inheritance.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c9a11-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9a11-122">Related sections</span></span>

<span data-ttu-id="c9a11-123">[クライアントアプリケーション](../../develop-client-apps.md)</span><span class="sxs-lookup"><span data-stu-id="c9a11-123">[Client Applications](../../develop-client-apps.md)</span></span>\
<span data-ttu-id="c9a11-124">Windows ベースのアプリケーションの開発の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="c9a11-124">Provides an overview of developing Windows-based applications.</span></span>
