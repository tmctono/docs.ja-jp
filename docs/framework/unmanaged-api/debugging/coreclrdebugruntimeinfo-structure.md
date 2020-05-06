---
title: CoreClrDebugRuntimeInfo 構造体
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860932"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="4f1ec-102">CoreClrDebugRuntimeInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="4f1ec-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="4f1ec-103">リモート コンピューター上のプロセスに読み込まれる共通言語ランタイム (CLR) インスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="4f1ec-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f1ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f1ec-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="4f1ec-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4f1ec-105">Members</span></span>  
  
|<span data-ttu-id="4f1ec-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4f1ec-106">Member</span></span>|<span data-ttu-id="4f1ec-107">説明</span><span class="sxs-lookup"><span data-stu-id="4f1ec-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="4f1ec-108">対象のコンピューターで実行されているリモート デバッグ プロキシによって割り当てられたランタイム識別子。</span><span class="sxs-lookup"><span data-stu-id="4f1ec-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f1ec-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f1ec-109">Requirements</span></span>  
 <span data-ttu-id="4f1ec-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f1ec-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f1ec-111">**ヘッダー:** Coreclrremoteデバッグインターフェイス .h</span><span class="sxs-lookup"><span data-stu-id="4f1ec-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4f1ec-112">**Library:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="4f1ec-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4f1ec-113">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4f1ec-113">**.NET Framework Versions:** 3.5 SP1</span></span>
