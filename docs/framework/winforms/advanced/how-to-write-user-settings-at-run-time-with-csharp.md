---
title: '方法: 実行時にユーザー設定を C# で書き込む'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 264fa9706f9255d7324cad6d02c36cc424e28995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778834"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="4bea8-102">方法: C での実行時にユーザー設定を書き込み\#</span><span class="sxs-lookup"><span data-stu-id="4bea8-102">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="4bea8-103">アプリケーション スコープの設定は読み取り専用であり、デザイン時、またはアプリケーション セッション間に .config ファイルを変更することによってのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="4bea8-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="4bea8-104">ただし、ユーザー スコープの設定は、プロパティ値を変更する場合と同様に、実行時に書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="4bea8-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="4bea8-105">新しい値は、アプリケーションのセッションの実行中に永続化します。</span><span class="sxs-lookup"><span data-stu-id="4bea8-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="4bea8-106">Save メソッドを呼び出すことによって、アプリケーション セッション間で、設定の変更を永続化することができます。</span><span class="sxs-lookup"><span data-stu-id="4bea8-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="4bea8-107">方法: 書き込みし、C での実行時にユーザー設定を永続化\#</span><span class="sxs-lookup"><span data-stu-id="4bea8-107">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="4bea8-108">この設定にアクセスし、この例で示すように、新しい値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4bea8-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="4bea8-109">アプリケーション セッション間で、設定の変更を永続化する場合は、この例で示すように Save メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4bea8-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="4bea8-110">ユーザー設定は、ユーザーの非表示のローカル アプリケーション データ フォルダーのサブフォルダー内のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4bea8-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bea8-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bea8-111">See also</span></span>

- [<span data-ttu-id="4bea8-112">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="4bea8-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="4bea8-113">方法: 実行時の設定の読み取りC#</span><span class="sxs-lookup"><span data-stu-id="4bea8-113">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="4bea8-114">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="4bea8-114">Application Settings Overview</span></span>](application-settings-overview.md)
