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
ms.openlocfilehash: 99b04060d4e7c14313655010dc4fbd5ce1c90487
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977653"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="ce6db-102">方法: アプリケーション セッション全体でアプリケーション スコープのプロパティを永続化および復元する</span><span class="sxs-lookup"><span data-stu-id="ce6db-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="ce6db-103">この例では、アプリケーションがシャット ダウンするタイミングとアプリケーション スコープのプロパティ、アプリケーションが [次へ] の起動を復元する方法は、アプリケーション スコープのプロパティを永続化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ce6db-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce6db-104">例</span><span class="sxs-lookup"><span data-stu-id="ce6db-104">Example</span></span>  
 <span data-ttu-id="ce6db-105">アプリケーションでは、アプリケーション スコープのプロパティを永続化し、分離ストレージからそれを復元します。</span><span class="sxs-lookup"><span data-stu-id="ce6db-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="ce6db-106">分離ストレージは、アプリケーション ファイルへのアクセス許可なしで安全に使用できる保護されたストレージ領域です。</span><span class="sxs-lookup"><span data-stu-id="ce6db-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="ce6db-107">*App.xaml*ファイルで定義、`App_Startup`メソッドのハンドラーとして、<xref:System.Windows.Application.Startup?displayProperty=nameWithType>イベント、および`App_Exit`メソッドのハンドラーとして、<xref:System.Windows.Application.Exit?displayProperty=nameWithType>イベントを強調表示されている行の最初の例で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="ce6db-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="ce6db-108">2 番目の例の一部を示しています、 *App.xaml.cs*と*App.xaml.vb*ファイルのコードを強調表示する、`App_Startup`メソッドで、アプリケーション スコープのプロパティ、および、復元`App_Exit`メソッドで、アプリケーション スコープのプロパティを保存します。</span><span class="sxs-lookup"><span data-stu-id="ce6db-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
