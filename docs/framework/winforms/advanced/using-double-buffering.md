---
title: ダブル バッファリングの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169921"
---
# <a name="using-double-buffering"></a><span data-ttu-id="61747-102">ダブル バッファリングの使用</span><span class="sxs-lookup"><span data-stu-id="61747-102">Using Double Buffering</span></span>
<span data-ttu-id="61747-103">ダブル バッファリングされたグラフィックスを使用して、複雑な描画操作が含まれているアプリケーションでちらつきを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="61747-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="61747-104">.NET Framework には、ダブル バッファリングの組み込みサポートが含まれています。 または、管理し、手動でグラフィックスをレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="61747-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61747-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="61747-105">In This Section</span></span>  
 [<span data-ttu-id="61747-106">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="61747-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="61747-107">二重のバッファリングの概念や概要の .NET Framework サポートをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="61747-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="61747-108">方法: フォームとコントロールのダブル バッファリングによってグラフィックスのちらつきを軽減します。</span><span class="sxs-lookup"><span data-stu-id="61747-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="61747-109">既定のダブル バッファリングを .NET Framework のサポートを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61747-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="61747-110">方法: バッファリングされたグラフィックスを手動で管理します。</span><span class="sxs-lookup"><span data-stu-id="61747-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="61747-111">アプリケーションでダブル バッファリングを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61747-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="61747-112">方法: バッファリングされたグラフィックスを手動で描画します。</span><span class="sxs-lookup"><span data-stu-id="61747-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="61747-113">ダブル バッファリングされたグラフィックスをレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61747-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="61747-114">参照</span><span class="sxs-lookup"><span data-stu-id="61747-114">Reference</span></span>  
 <span data-ttu-id="61747-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ダブル バッファリングをできる制御メソッド。</span><span class="sxs-lookup"><span data-stu-id="61747-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="61747-116"><xref:System.Drawing.BufferedGraphicsContext> グラフィックス バッファーを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="61747-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="61747-117">アプリケーション ドメインのバッファリングされたグラフィックス コンテキストへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="61747-117">Provides access to the buffered graphics context for a application domain.</span></span>
