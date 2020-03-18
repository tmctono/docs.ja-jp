---
title: Storeadm.exe (分離ストレージ ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: 46e846eaf92835fb2a9130b85ed20749934ca5a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715714"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="1f5fc-102">Storeadm.exe (分離ストレージ ツール)</span><span class="sxs-lookup"><span data-stu-id="1f5fc-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="1f5fc-103">分離ストレージ ツールは、現在のユーザーに関するすべての既存ストアの一覧表示または削除を行います。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="1f5fc-104">このツールは、Visual Studio と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="1f5fc-105">このツールを実行するには、Visual Studio 用開発者コマンド プロンプト (または Windows 7 の Visual Studio コマンド プロンプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="1f5fc-106">詳細については、「[コマンド プロンプト](developer-command-prompt-for-vs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="1f5fc-107">コマンド プロンプトに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f5fc-108">構文</span><span class="sxs-lookup"><span data-stu-id="1f5fc-108">Syntax</span></span>  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f5fc-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f5fc-109">Parameters</span></span>  
  
|<span data-ttu-id="1f5fc-110">オプション</span><span class="sxs-lookup"><span data-stu-id="1f5fc-110">Option</span></span>|<span data-ttu-id="1f5fc-111">[説明]</span><span class="sxs-lookup"><span data-stu-id="1f5fc-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1f5fc-112">**/h** **[elp]**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-112">**/h**[**elp**]</span></span>|<span data-ttu-id="1f5fc-113">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="1f5fc-114">**/list**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-114">**/list**</span></span>|<span data-ttu-id="1f5fc-115">現在のユーザーに関するすべての既存ストアを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="1f5fc-116">このユーザーによって実行された、すべてのアプリケーションまたはアセンブリに関するストアなどが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="1f5fc-117">**/machine**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-117">**/machine**</span></span>|<span data-ttu-id="1f5fc-118">コンピューター ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-118">Selects the machine store.</span></span> <span data-ttu-id="1f5fc-119">このオプションを **/list** または **/remove** オプションと一緒に使用すると、それらのアクションをマシン ストアに適用する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="1f5fc-120">.NET Framework 2.0 で新たに追加されました。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="1f5fc-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-121">**/quiet**</span></span>|<span data-ttu-id="1f5fc-122">クワイエット モードを指定します。このモードでは、情報の出力が中止され、エラー メッセージだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="1f5fc-123">**/remove**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-123">**/remove**</span></span>|<span data-ttu-id="1f5fc-124">現在のユーザーに関するすべての既存ストアを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="1f5fc-125">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-125">**/roaming**</span></span>|<span data-ttu-id="1f5fc-126">ローミング ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-126">Selects the roaming store.</span></span> <span data-ttu-id="1f5fc-127">このオプションを **/list** または **/remove** オプションと一緒に使用すると、それらのアクションをローミング ストアに適用する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="1f5fc-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="1f5fc-128">**/?**</span></span>|<span data-ttu-id="1f5fc-129">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f5fc-130">解説</span><span class="sxs-lookup"><span data-stu-id="1f5fc-130">Remarks</span></span>  
 <span data-ttu-id="1f5fc-131">オプションを指定せずにコマンド ラインから Storeadm.exe を実行すると、Storeadm.exe に関する構文とオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="1f5fc-132">一般に、 **/list** オプションと **/remove** オプションは同時に使用されますが、2 つ以上のオプションを指定した場合、それらのオプションはコマンド ラインに表示されている順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="1f5fc-133">アプリケーションは、ユーザー ストアまたはコンピューター ストアのいずれかを選択して保存できます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
- <span data-ttu-id="1f5fc-134">ローカル ストアは、該当するユーザーに関するデータのローミングが有効な場合でも、ローミングされないことが保証されている場所 (Windows 2000 以降) に存在します。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
- <span data-ttu-id="1f5fc-135">ローミング ストアは、ローミングできる場所に存在しますが、ローミングできるのは、Windows NT の管理機能を通じて、該当するユーザーに対してローミングが有効化されている場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
- <span data-ttu-id="1f5fc-136">コンピューター ストアは、コンピューターのすべてのユーザーに共通で、コンピューターの共通ディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1f5fc-137">コンピューター ストアは .NET Framework Version 2.0 で新たに追加されました。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="1f5fc-138">ユーザーに対してローミングが実際に有効になっているかどうかは、Storeadm.exe の管理に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="1f5fc-139">オプションを指定せずに Storeadm.exe を実行した場合、すべてのアクションがローカル ストアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="1f5fc-140">**/roaming** オプションを指定した場合は、すべてのアクションが、ローミングできるストアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="1f5fc-141">**/machine** オプションを指定してこのツールを実行すると、すべてのアクションがコンピューター ストアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f5fc-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5fc-142">参照</span><span class="sxs-lookup"><span data-stu-id="1f5fc-142">See also</span></span>

- [<span data-ttu-id="1f5fc-143">ツール</span><span class="sxs-lookup"><span data-stu-id="1f5fc-143">Tools</span></span>](index.md)
- [<span data-ttu-id="1f5fc-144">分離ストレージ</span><span class="sxs-lookup"><span data-stu-id="1f5fc-144">Isolated Storage</span></span>](../../standard/io/isolated-storage.md)
- [<span data-ttu-id="1f5fc-145">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="1f5fc-145">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
