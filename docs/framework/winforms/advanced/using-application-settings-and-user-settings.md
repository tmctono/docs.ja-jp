---
title: アプリケーション設定とユーザー設定の使用
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: ea6994e653b3a06239634f5a0fddea84a07086e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777183"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="8eebe-102">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="8eebe-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="8eebe-103">以降、.NET Framework 2.0 では、作成し、アプリケーションの実行のセッション間で保持されている値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8eebe-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="8eebe-104">これらの値と呼ばれる*設定*します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-104">These values are called *settings*.</span></span> <span data-ttu-id="8eebe-105">設定は、ユーザー設定を表すことができますか、貴重な情報、アプリケーションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eebe-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="8eebe-106">たとえば、一連のアプリケーションの配色のユーザー設定を保存している設定を作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8eebe-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="8eebe-107">または、アプリケーションを使用するデータベースを指定する接続文字列を格納する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8eebe-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="8eebe-108">設定は、両方に個々 のユーザーの設定を格納するプロファイルを作成して、コードの外部のアプリケーションに不可欠な情報の保存を許可します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="8eebe-109">このセクションのトピックでは、デザイン時の設定を使用して、時間を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8eebe-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8eebe-110">In This Section</span></span>  
 [<span data-ttu-id="8eebe-111">方法: デザイン時に新しい設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-111">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="8eebe-112">Visual Studio を使用して、アプリケーションの新しい設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="8eebe-113">方法: デザイン時に既存の設定の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="8eebe-114">Visual Studio を使用して、既存の設定の値を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="8eebe-115">方法: アプリケーション セッション間での設定の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="8eebe-116">アプリケーション セッション間でコンパイルされたアプリケーションの設定の値を変更する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="8eebe-117">方法: 実行時の設定の読み取りC#</span><span class="sxs-lookup"><span data-stu-id="8eebe-117">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="8eebe-118">使用して設定を読み取るコードを使用する方法について説明しますC#します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="8eebe-119">方法: 実行時にユーザー設定を書き込みC#</span><span class="sxs-lookup"><span data-stu-id="8eebe-119">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="8eebe-120">コードを使用して記述し、でユーザー設定の値を保存する方法について説明しますC#します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="8eebe-121">方法: アプリケーションに複数の設定セットを追加します。C#</span><span class="sxs-lookup"><span data-stu-id="8eebe-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="8eebe-122">使用したアプリケーションに複数の設定セットを追加する方法の詳細をC#します。</span><span class="sxs-lookup"><span data-stu-id="8eebe-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eebe-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8eebe-123">See also</span></span>

- [<span data-ttu-id="8eebe-124">Windows フォームのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="8eebe-124">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
