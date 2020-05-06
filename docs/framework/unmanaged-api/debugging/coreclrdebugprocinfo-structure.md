---
title: CoreClrDebugProcInfo 構造体
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 40dbfc60f8bde1198fd56a4a8aeed1dd6879d1ae
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795626"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="9d4e5-102">CoreClrDebugProcInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="9d4e5-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="9d4e5-103">リモート コンピューターで実行されているプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4e5-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d4e5-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="9d4e5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9d4e5-105">Members</span></span>  
  
|<span data-ttu-id="9d4e5-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9d4e5-106">Member</span></span>|<span data-ttu-id="9d4e5-107">説明</span><span class="sxs-lookup"><span data-stu-id="9d4e5-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="9d4e5-108">OS によって割り当てられたプロセス識別子。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="9d4e5-109">対象のコンピューターで実行されているリモート デバッグ プロキシによって割り当てられたプロセス識別子。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="9d4e5-110">この識別子は OS 識別子よりも少ない頻度で再利用されます。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="9d4e5-111">プロセスのコマンド ライン。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-111">Command-line of the process.</span></span> <span data-ttu-id="9d4e5-112">このメンバーは切り詰められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d4e5-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="9d4e5-113">Requirements</span></span>  
 <span data-ttu-id="9d4e5-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d4e5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d4e5-115">**ヘッダー:** Coreclrremoteデバッグインターフェイス .h</span><span class="sxs-lookup"><span data-stu-id="9d4e5-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9d4e5-116">**Library:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="9d4e5-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9d4e5-117">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9d4e5-117">**.NET Framework Versions:** 3.5 SP1</span></span>
