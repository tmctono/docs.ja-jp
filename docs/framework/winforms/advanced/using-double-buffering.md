---
title: ダブル バッファリングの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716282"
---
# <a name="using-double-buffering"></a><span data-ttu-id="ff907-102">ダブル バッファリングの使用</span><span class="sxs-lookup"><span data-stu-id="ff907-102">Using Double Buffering</span></span>
<span data-ttu-id="ff907-103">ダブル バッファリングされたグラフィックスを使用して、複雑な描画操作が含まれているアプリケーションでちらつきを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="ff907-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="ff907-104">.NET Framework には、ダブル バッファリングの組み込みサポートが含まれています。 または、管理し、手動でグラフィックスをレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="ff907-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff907-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff907-105">In This Section</span></span>  
 [<span data-ttu-id="ff907-106">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="ff907-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="ff907-107">二重のバッファリングの概念や概要の .NET Framework サポートをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ff907-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="ff907-108">方法: フォームとコントロールのダブル バッファリングによってグラフィックスのちらつきを軽減します。</span><span class="sxs-lookup"><span data-stu-id="ff907-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="ff907-109">既定のダブル バッファリングを .NET Framework のサポートを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff907-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="ff907-110">方法: バッファリングされたグラフィックスを手動で管理します。</span><span class="sxs-lookup"><span data-stu-id="ff907-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="ff907-111">アプリケーションでダブル バッファリングを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff907-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="ff907-112">方法: バッファリングされたグラフィックスを手動で描画します。</span><span class="sxs-lookup"><span data-stu-id="ff907-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="ff907-113">ダブル バッファリングされたグラフィックスをレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff907-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff907-114">参照</span><span class="sxs-lookup"><span data-stu-id="ff907-114">Reference</span></span>  
 <span data-ttu-id="ff907-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="ff907-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="ff907-116">ダブル バッファリングをできる制御メソッド。</span><span class="sxs-lookup"><span data-stu-id="ff907-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="ff907-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="ff907-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="ff907-118">グラフィックス バッファーを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff907-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="ff907-119">アプリケーション ドメインのバッファリングされたグラフィックス コンテキストへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff907-119">Provides access to the buffered graphics context for a application domain.</span></span>
