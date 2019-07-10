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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b58832e110f67a54d3bd57a7284b2e26e43d6bf7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739408"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="700b7-102">CoreClrDebugRuntimeInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="700b7-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="700b7-103">リモート コンピューター上のプロセスに読み込まれる共通言語ランタイム (CLR) インスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="700b7-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="700b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="700b7-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="700b7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="700b7-105">Members</span></span>  
  
|<span data-ttu-id="700b7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="700b7-106">Member</span></span>|<span data-ttu-id="700b7-107">説明</span><span class="sxs-lookup"><span data-stu-id="700b7-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="700b7-108">対象のコンピューターで実行されているリモート デバッグ プロキシによって割り当てられたランタイム識別子。</span><span class="sxs-lookup"><span data-stu-id="700b7-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="700b7-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="700b7-109">Requirements</span></span>  
 <span data-ttu-id="700b7-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="700b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="700b7-111">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="700b7-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="700b7-112">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="700b7-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="700b7-113">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="700b7-113">**.NET Framework Versions:** 3.5 SP1</span></span>
