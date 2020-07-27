---
title: UI オートメーションのセキュリティの概要
description: 「Microsoft UI オートメーションのセキュリティモデルの概要」を参照してください。 ユーザーアカウント制御、高い特権を必要とするタスク、およびマニフェストファイルについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: d483f282db8ce8e5653d6d83361fa44df05f63f5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163148"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="6a868-104">UI オートメーションのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="6a868-104">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="6a868-105">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="6a868-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6a868-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6a868-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="6a868-107">この概要では、Windows Vista ののセキュリティモデルについて説明し [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] ます。</span><span class="sxs-lookup"><span data-stu-id="6a868-107">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="6a868-108">ユーザー アカウント制御</span><span class="sxs-lookup"><span data-stu-id="6a868-108">User Account Control</span></span>

<span data-ttu-id="6a868-109">セキュリティは Windows Vista の主な焦点であり、イノベーションの中では、より高い特権を必要とするアプリケーションやサービスの実行がブロックされることなく、ユーザーが標準 (管理者以外の) ユーザーとして実行できるようにする機能があります。</span><span class="sxs-lookup"><span data-stu-id="6a868-109">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="6a868-110">Windows Vista では、ほとんどのアプリケーションに標準トークンまたは管理トークンが付属しています。</span><span class="sxs-lookup"><span data-stu-id="6a868-110">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="6a868-111">アプリケーションが管理アプリケーションとして識別できない場合は、既定で標準のアプリケーションとして起動されます。</span><span class="sxs-lookup"><span data-stu-id="6a868-111">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="6a868-112">管理対象として識別されたアプリケーションを起動できるようになる前に、Windows Vista では、昇格されたアプリケーションの実行に同意するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="6a868-112">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="6a868-113">ユーザーがローカル管理者グループのメンバーである場合でも、同意を求めるメッセージは既定で表示されます。これは、管理者の資格情報を必要とするアプリケーションまたはシステム コンポーネントが実行の許可を要求するまで、管理者は標準ユーザーとして実行するためです。</span><span class="sxs-lookup"><span data-stu-id="6a868-113">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="6a868-114">より高い特権が必要なタスク</span><span class="sxs-lookup"><span data-stu-id="6a868-114">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="6a868-115">ユーザーが管理者特権を必要とするタスクを実行しようとすると、Windows Vista では、ユーザーに続行の同意を求めるダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a868-115">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="6a868-116">このダイアログ ボックスは、悪意のあるソフトウェアがユーザー入力をシミュレートできないように、プロセス間通信から保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a868-116">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="6a868-117">同様に、デスクトップのログオン画面は、通常は他のプロセスからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6a868-117">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="6a868-118">UI オートメーション クライアントは、他のプロセスと通信する必要があります。プロセスによっては、より高い特権レベルで実行している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a868-118">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="6a868-119">クライアントにも、通常は他のプロセスによって表示できないシステム ダイアログ ボックスへのアクセスが必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a868-119">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="6a868-120">そのため、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] クライアントはシステムによって信頼されている必要があり、特別な特権で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a868-120">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="6a868-121">より高い権限レベルで実行されているアプリケーションと通信する信頼を得るためには、アプリケーションに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a868-121">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="6a868-122">マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="6a868-122">Manifest Files</span></span>

<span data-ttu-id="6a868-123">保護されたシステム UI にアクセスするには、次のように、タグに属性を含むマニフェストファイルを使用してアプリケーションをビルドする必要があり `uiAccess` `requestedExecutionLevel` ます。</span><span class="sxs-lookup"><span data-stu-id="6a868-123">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="6a868-124">このコードの `level` 属性の値は一例にすぎません。</span><span class="sxs-lookup"><span data-stu-id="6a868-124">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="6a868-125">`uiAccess`既定値は "false" です。つまり、属性を省略した場合、またはアセンブリのマニフェストが存在しない場合、アプリケーションは保護された UI にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a868-125">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
