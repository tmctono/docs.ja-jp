---
title: StackOverflowInfo 構造体
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105917"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="492cb-102">StackOverflowInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="492cb-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="492cb-103">発生したオーバーフローの種類とオーバーフローによってスローされた例外に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="492cb-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="492cb-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="492cb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="492cb-105">Members</span></span>  
  
|<span data-ttu-id="492cb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="492cb-106">Member</span></span>|<span data-ttu-id="492cb-107">説明</span><span class="sxs-lookup"><span data-stu-id="492cb-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="492cb-108">オーバーフローの種類を指定する[StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="492cb-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="492cb-109">Win32 `EXCEPTION_POINTERS` オブジェクトへのポインター。このオブジェクトには、例外の説明がコンピューターに依存しない例外レコードと、例外の発生時にプロセッサコンテキストのコンピューターに依存する記述を持つコンテキストレコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="492cb-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="492cb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="492cb-110">Remarks</span></span>  
 <span data-ttu-id="492cb-111">`StackOverflowInfo` オブジェクトは、`Event_StackOverflow` イベントの[Iactiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="492cb-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="492cb-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="492cb-112">Requirements</span></span>  
 <span data-ttu-id="492cb-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="492cb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="492cb-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="492cb-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="492cb-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="492cb-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="492cb-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492cb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492cb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="492cb-117">See also</span></span>

- [<span data-ttu-id="492cb-118">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="492cb-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
