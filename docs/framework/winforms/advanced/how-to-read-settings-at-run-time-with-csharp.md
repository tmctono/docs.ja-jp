---
title: '方法: 実行時に設定を C# で読み取る'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966918"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="8fea6-102">方法: C での実行時に設定の読み取り\#</span><span class="sxs-lookup"><span data-stu-id="8fea6-102">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="8fea6-103">アプリケーション スコープの設定とユーザー スコープの設定は、どちらも実行時に Properties オブジェクトを使用して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8fea6-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="8fea6-104">Properties オブジェクトは、プロジェクトのすべての既定の設定を、Properties.Settings.Default メンバーを介して公開します。</span><span class="sxs-lookup"><span data-stu-id="8fea6-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="8fea6-105">C での実行時に設定を読み取る\#</span><span class="sxs-lookup"><span data-stu-id="8fea6-105">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="8fea6-106">Properties.Settings.Default メンバーを介して適切な設定にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8fea6-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="8fea6-107">BackColor プロパティに `myColor` という名前の設定を割り当てる方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="8fea6-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="8fea6-108">この例を実行する前に、`myColor` という名前の `System.Drawing.Color` 型の設定を含む設定ファイルを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fea6-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="8fea6-109">設定ファイルを作成する方法の詳細については、次を参照してください[How To:。デザイン時に新しい設定を作成](how-to-create-a-new-setting-at-design-time.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fea6-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fea6-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fea6-110">See also</span></span>

- [<span data-ttu-id="8fea6-111">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="8fea6-111">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="8fea6-112">方法: 実行時にユーザー設定を書き込みC#</span><span class="sxs-lookup"><span data-stu-id="8fea6-112">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="8fea6-113">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="8fea6-113">Application Settings Overview</span></span>](application-settings-overview.md)
