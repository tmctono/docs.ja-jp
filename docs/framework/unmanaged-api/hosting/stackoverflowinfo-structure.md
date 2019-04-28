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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac0f5d522a24394369583692f8c564254529bf13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796046"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="fcd54-102">StackOverflowInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="fcd54-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="fcd54-103">オーバーフローによりスローされた例外でオーバーフローが発生しましたが、情報の種類を格納します。</span><span class="sxs-lookup"><span data-stu-id="fcd54-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd54-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcd54-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="fcd54-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fcd54-105">Members</span></span>  
  
|<span data-ttu-id="fcd54-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fcd54-106">Member</span></span>|<span data-ttu-id="fcd54-107">説明</span><span class="sxs-lookup"><span data-stu-id="fcd54-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="fcd54-108">値、 [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)オーバーフローの種類を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="fcd54-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="fcd54-109">Win32 へのポインター`EXCEPTION_POINTERS`例外レコードと、例外のマシンに依存しない説明および例外発生時にプロセッサのコンテキストのマシンに依存する説明を持つコンテキスト レコードを含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fcd54-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcd54-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="fcd54-110">Remarks</span></span>  
 <span data-ttu-id="fcd54-111">A`StackOverflowInfo`にオブジェクトが渡される、 [iactiononclrevent::onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)メソッド`Event_StackOverflow`イベント。</span><span class="sxs-lookup"><span data-stu-id="fcd54-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd54-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcd54-112">Requirements</span></span>  
 <span data-ttu-id="fcd54-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd54-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd54-114">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="fcd54-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="fcd54-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fcd54-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcd54-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd54-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd54-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcd54-117">See also</span></span>

- [<span data-ttu-id="fcd54-118">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="fcd54-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
