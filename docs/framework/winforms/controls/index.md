---
title: Windows フォーム コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls
- controls [Windows Forms]
- Windows Forms controls, about Windows Forms controls
ms.assetid: f050de8f-4ebd-4042-94b8-edf9a1dbd52a
ms.openlocfilehash: 1088781a7780df71773b01a3816f024562abfcaf
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69986984"
---
# <a name="windows-forms-controls"></a><span data-ttu-id="f0e44-102">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="f0e44-102">Windows Forms controls</span></span>

<span data-ttu-id="f0e44-103">Windows フォーム アプリケーションのユーザー インターフェイスを設計および変更するときは、コントロールを追加、整列、配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e44-103">As you design and modify the user interface of your Windows Forms applications, you will need to add, align, and position controls.</span></span> <span data-ttu-id="f0e44-104">コントロールは、フォーム オブジェクトに含まれるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f0e44-104">Controls are objects that are contained within form objects.</span></span> <span data-ttu-id="f0e44-105">コントロールの各種類には、そのコントロールを特定の目的に適したものにする固有のプロパティ、メソッド、イベントのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="f0e44-105">Each type of control has its own set of properties, methods, and events that make it suitable for a particular purpose.</span></span> <span data-ttu-id="f0e44-106">デザイナーでコントロールを操作し、実行時にコントロールを動的に追加するコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="f0e44-106">You can manipulate controls in the designer and write code to add controls dynamically at run time.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f0e44-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f0e44-107">In this section</span></span>

<span data-ttu-id="f0e44-108">[Windows フォームへのコントロールの追加](putting-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-108">[Putting Controls on Windows Forms](putting-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="f0e44-109">フォームへのコントロールの追加に関連するリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="f0e44-109">Provides links related to putting controls on forms.</span></span>

<span data-ttu-id="f0e44-110">[Windows フォーム上のコントロールの配置](how-to-align-multiple-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-110">[Arranging Controls on Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="f0e44-111">フォーム上のコントロールの配置に関連する記事。</span><span class="sxs-lookup"><span data-stu-id="f0e44-111">Articles related to arranging controls on forms.</span></span>

<span data-ttu-id="f0e44-112">[個々の Windows フォームコントロールのラベル付けとそれらへのショートカットの提供](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-112">[Labeling Individual Windows Forms Controls and Providing Shortcuts to Them](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span></span>\
<span data-ttu-id="f0e44-113">キーボード ショートカット、コントロールのテキスト ラベル、修飾キーの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0e44-113">Describes the uses of keyboard shortcuts, text labels on controls, and modifier keys.</span></span>

<span data-ttu-id="f0e44-114">[Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-114">[Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md)</span></span>\
<span data-ttu-id="f0e44-115">Windows フォームで使うことができるコントロールの一覧、および各コントロールで実行できる基本的な事柄を示します。</span><span class="sxs-lookup"><span data-stu-id="f0e44-115">Lists the controls that work with Windows Forms, and basic things you can accomplish with each control.</span></span>

<span data-ttu-id="f0e44-116">[.NET Framework を使用したカスタム Windows フォーム コントロールの開発](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-116">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="f0e44-117">カスタム Windows フォーム コントロールの開発に役立つ背景情報とサンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="f0e44-117">Provides background information and samples to help users develop custom Windows Forms controls.</span></span>

<span data-ttu-id="f0e44-118">[デザイン時の Windows フォーム コントロールの開発](developing-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-118">[Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="f0e44-119">デザインと継承を使ってカスタム コントロールを作成するための手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0e44-119">Describes techniques for creating custom controls through design and inheritance.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f0e44-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0e44-120">Related sections</span></span>

<span data-ttu-id="f0e44-121">[クライアントアプリケーション](../../develop-client-apps.md)</span><span class="sxs-lookup"><span data-stu-id="f0e44-121">[Client Applications](../../develop-client-apps.md)</span></span>\
<span data-ttu-id="f0e44-122">Windows ベースのアプリケーションの開発の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="f0e44-122">Provides an overview of developing Windows-based applications.</span></span>
