---
title: USER_THREAD 構造体
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914707"
---
# <a name="userthread-structure"></a><span data-ttu-id="d8b98-102">USER_THREAD 構造体</span><span class="sxs-lookup"><span data-stu-id="d8b98-102">USER_THREAD Structure</span></span>
<span data-ttu-id="d8b98-103">デバッガー スレッドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d8b98-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="d8b98-104">詳細については、次を参照してください。、 [inotifysource 2::setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d8b98-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b98-105">構文</span><span class="sxs-lookup"><span data-stu-id="d8b98-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="d8b98-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d8b98-106">Members</span></span>  
  
|<span data-ttu-id="d8b98-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="d8b98-107">Member</span></span>|<span data-ttu-id="d8b98-108">説明</span><span class="sxs-lookup"><span data-stu-id="d8b98-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="d8b98-109">スレッドのバッファーのアドレス。</span><span class="sxs-lookup"><span data-stu-id="d8b98-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="d8b98-110">(バイト単位) のスレッドのバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="d8b98-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="d8b98-111">スレッド id です。</span><span class="sxs-lookup"><span data-stu-id="d8b98-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8b98-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8b98-112">Requirements</span></span>  
 <span data-ttu-id="d8b98-113">**ヘッダー:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d8b98-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b98-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8b98-114">See also</span></span>

- [<span data-ttu-id="d8b98-115">SetNotifyFilter メソッド</span><span class="sxs-lookup"><span data-stu-id="d8b98-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="d8b98-116">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="d8b98-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
