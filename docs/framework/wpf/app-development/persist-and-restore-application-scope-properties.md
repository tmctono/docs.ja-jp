---
title: '方法: アプリケーション セッション全体でアプリケーション スコープのプロパティを永続化および復元する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666724"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="9fcc3-102">方法: アプリケーション セッション全体でアプリケーション スコープのプロパティを永続化および復元する</span><span class="sxs-lookup"><span data-stu-id="9fcc3-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="9fcc3-103">この例では、アプリケーションのシャットダウン時にアプリケーションスコープのプロパティを永続化する方法と、アプリケーションの次回起動時にアプリケーションスコープのプロパティを復元する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9fcc3-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fcc3-104">例</span><span class="sxs-lookup"><span data-stu-id="9fcc3-104">Example</span></span>  
 <span data-ttu-id="9fcc3-105">アプリケーションは、アプリケーションスコープのプロパティをに永続化し、分離ストレージから復元します。</span><span class="sxs-lookup"><span data-stu-id="9fcc3-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="9fcc3-106">分離ストレージは、ファイルアクセス許可のないアプリケーションで安全に使用できる、保護されたストレージ領域です。</span><span class="sxs-lookup"><span data-stu-id="9fcc3-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="9fcc3-107">*App.xaml*ファイル`App_Startup`は、 <xref:System.Windows.Application.Startup?displayProperty=nameWithType>イベントのハンドラーとしてメソッドを定義し`App_Exit` 、最初の例の強調表示され<xref:System.Windows.Application.Exit?displayProperty=nameWithType>た行に示すように、そのイベントのハンドラーとしてメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="9fcc3-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="9fcc3-108">2番目の例は、 *App.xaml.cs*ファイルと app.xaml ファイルの一部を示して*います。* このメソッド`App_Startup`は、アプリケーションスコープのプロパティを`App_Exit`復元するメソッドのコードを強調表示し、メソッドを使用して、アプリケーションスコープを保存します。属性.</span><span class="sxs-lookup"><span data-stu-id="9fcc3-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
