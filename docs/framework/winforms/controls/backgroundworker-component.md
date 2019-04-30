---
title: BackgroundWorker コンポーネント
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 0baf54d27cf33eef7e4df7019ee98b42eba40205
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011802"
---
# <a name="backgroundworker-component"></a><span data-ttu-id="d3101-102">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d3101-102">BackgroundWorker Component</span></span>
<span data-ttu-id="d3101-103">`BackgroundWorker`コンポーネントにより、フォームまたはコントロールを非同期的に操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3101-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3101-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d3101-104">In This Section</span></span>  
 [<span data-ttu-id="d3101-105">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="d3101-105">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="d3101-106">について説明します、`BackgroundWorker`コンポーネントで、アプリケーションのメイン UI スレッドから別のスレッドで非同期的に ("バック グラウンドで")、時間のかかる操作を実行する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d3101-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="d3101-107">チュートリアル: バック グラウンドで操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3101-107">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="d3101-108">使用する方法を示します、`BackgroundWorker`別のスレッドで時間のかかる操作を実行するデザイナーでコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d3101-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="d3101-109">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="d3101-109">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="d3101-110">使用する方法を示します、`BackgroundWorker`コンポーネントを別のスレッドで時間のかかる操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3101-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="d3101-111">チュートリアル: バック グラウンド操作を使用するフォームの実装</span><span class="sxs-lookup"><span data-stu-id="d3101-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="d3101-112">数学的計算を非同期にはデザイナーを使用してアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3101-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="d3101-113">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="d3101-113">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="d3101-114">数学的計算を非同期的に実行するアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3101-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="d3101-115">方法: バック グラウンドでファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d3101-115">How to: Download a File in the Background</span></span>](how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="d3101-116">使用する方法を示します、`BackgroundWorker`別のスレッドでファイルをダウンロードするコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d3101-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d3101-117">参照</span><span class="sxs-lookup"><span data-stu-id="d3101-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="d3101-118">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d3101-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="d3101-119">データを保持する型を記述、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント。</span><span class="sxs-lookup"><span data-stu-id="d3101-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="d3101-120">データを保持する型を記述、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="d3101-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3101-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3101-121">Related Sections</span></span>  
 [<span data-ttu-id="d3101-122">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="d3101-122">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="d3101-123">どの非同期パターンを使用可能マルチ スレッド アプリケーションの利点、マルチ スレッド デザイン固有の複雑な問題の多くについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d3101-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
