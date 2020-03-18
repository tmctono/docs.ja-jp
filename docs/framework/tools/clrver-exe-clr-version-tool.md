---
title: Clrver.exe (CLR バージョン ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: bfc612ef5455e1b4a03d15fd99a8a1873d2c7c08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715795"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="cac03-102">Clrver.exe (CLR バージョン ツール)</span><span class="sxs-lookup"><span data-stu-id="cac03-102">Clrver.exe (CLR Version Tool)</span></span>
<span data-ttu-id="cac03-103">CLR バージョン ツール (Clrver.exe) は、コンピューターにインストールされている共通言語ランタイム (CLR: Common Language Runtime) のすべてのバージョンを報告します。</span><span class="sxs-lookup"><span data-stu-id="cac03-103">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="cac03-104">このツールは、Visual Studio と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cac03-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="cac03-105">このツールを実行するには、Visual Studio 用開発者コマンド プロンプト (または Windows 7 の Visual Studio コマンド プロンプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cac03-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="cac03-106">詳細については、「[コマンド プロンプト](developer-command-prompt-for-vs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac03-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="cac03-107">コマンド プロンプトに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cac03-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac03-108">構文</span><span class="sxs-lookup"><span data-stu-id="cac03-108">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="cac03-109">オプション</span><span class="sxs-lookup"><span data-stu-id="cac03-109">Options</span></span>  
  
|<span data-ttu-id="cac03-110">オプション</span><span class="sxs-lookup"><span data-stu-id="cac03-110">Option</span></span>|<span data-ttu-id="cac03-111">[説明]</span><span class="sxs-lookup"><span data-stu-id="cac03-111">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="cac03-112">CLR を使用しているコンピューター上のすべてのプロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="cac03-112">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="cac03-113">*pid*</span><span class="sxs-lookup"><span data-stu-id="cac03-113">*pid*</span></span>|<span data-ttu-id="cac03-114">指定したプロセス ID (PID) のプロセスで使用されている CLR のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="cac03-114">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="cac03-115">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="cac03-115">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cac03-116">解説</span><span class="sxs-lookup"><span data-stu-id="cac03-116">Remarks</span></span>  
 <span data-ttu-id="cac03-117">オプションを指定せずに Clrver.exe を呼び出した場合、インストールされている CLR のすべてのバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cac03-117">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="cac03-118">別のユーザーの PID を指定する場合、バージョン情報を取得するには、管理アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="cac03-118">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cac03-119">Windows Vista 以降では、ユーザー アカウント制御 (UAC: User Account Control) でユーザーの権限が決定されます。</span><span class="sxs-lookup"><span data-stu-id="cac03-119">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="cac03-120">ユーザーが組み込みの Administrators グループのメンバーである場合、そのユーザーには標準ユーザー アクセス トークンおよび管理者アクセス トークンの 2 つのランタイム アクセス トークンが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="cac03-120">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="cac03-121">既定では、ユーザーは標準ユーザー ロールに所属します。</span><span class="sxs-lookup"><span data-stu-id="cac03-121">By default, you are in the standard user role.</span></span> <span data-ttu-id="cac03-122">管理アクセス許可を必要とするコードを実行するには、最初に、ユーザーの権限を標準ユーザーから管理者に昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cac03-122">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="cac03-123">この操作は、コマンド プロンプトの起動時にコマンド プロンプト アイコンを右クリックし、管理者として実行することを指定して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cac03-123">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="cac03-124">SYSTEM、LOCAL SERVICE、および NETWORK SERVICE の各プロセスの CLR バージョンを確認しようとすると、PID が存在しないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cac03-124">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cac03-125">例</span><span class="sxs-lookup"><span data-stu-id="cac03-125">Examples</span></span>  
 <span data-ttu-id="cac03-126">コンピューターにインストールされている CLR のすべてのバージョンを表示するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cac03-126">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="cac03-127">プロセス 128 で使用されている CLR のバージョンを表示するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cac03-127">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="cac03-128">すべてのマネージド プロセスとそれらのプロセスで使用されている CLR のバージョンを表示するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cac03-128">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="cac03-129">参照</span><span class="sxs-lookup"><span data-stu-id="cac03-129">See also</span></span>

- [<span data-ttu-id="cac03-130">ツール</span><span class="sxs-lookup"><span data-stu-id="cac03-130">Tools</span></span>](index.md)
- [<span data-ttu-id="cac03-131">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="cac03-131">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
