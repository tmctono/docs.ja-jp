---
title: '方法: 実行時に設定を C# で読み取る'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710228"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="94dfa-102">方法: 実行時に C を使用して設定を読み取る\#</span><span class="sxs-lookup"><span data-stu-id="94dfa-102">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="94dfa-103">アプリケーション スコープの設定とユーザー スコープの設定は、どちらも実行時に Properties オブジェクトを使用して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="94dfa-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="94dfa-104">Properties オブジェクトは、プロジェクトのすべての既定の設定を、定義されているプロジェクトの既定の名前空間にある default メンバーを介して公開します。</span><span class="sxs-lookup"><span data-stu-id="94dfa-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member in the default namespace of the project they are defined in.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="94dfa-105">実行時に C を使用して設定を読み取るには\#</span><span class="sxs-lookup"><span data-stu-id="94dfa-105">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="94dfa-106">Properties.Settings.Default メンバーを介して適切な設定にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="94dfa-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="94dfa-107">BackColor プロパティに `myColor` という名前の設定を割り当てる方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="94dfa-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="94dfa-108">この例を実行する前に、`myColor` という名前の `System.Drawing.Color` 型の設定を含む設定ファイルを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="94dfa-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="94dfa-109">設定ファイルの作成の詳細について[は、「方法:デザイン時](how-to-create-a-new-setting-at-design-time.md)に新しい設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="94dfa-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="94dfa-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="94dfa-110">See also</span></span>

- [<span data-ttu-id="94dfa-111">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="94dfa-111">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="94dfa-112">方法: 実行時にユーザー設定を作成するC#</span><span class="sxs-lookup"><span data-stu-id="94dfa-112">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="94dfa-113">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="94dfa-113">Application Settings Overview</span></span>](application-settings-overview.md)
