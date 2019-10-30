---
title: PFN_CLRDataCreateInstance 関数ポインター
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
ms.openlocfilehash: 426a8acf2e9319725cf592db00dc97c8960bca4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139161"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="fa79d-102">PFN_CLRDataCreateInstance 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="fa79d-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="fa79d-103">指定されたターゲット項目のインターフェイスオブジェクトを作成する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="fa79d-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa79d-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa79d-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa79d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa79d-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="fa79d-106">からインスタンス化するインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="fa79d-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="fa79d-107">からインターフェイスオブジェクトの作成対象となる項目を表す、ユーザーによって実装された[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fa79d-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="fa79d-108">入出力返されたインターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fa79d-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa79d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa79d-109">Remarks</span></span>  
 <span data-ttu-id="fa79d-110">`ICLRDataTarget` オブジェクトは、デバッグアプリケーションのライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="fa79d-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="fa79d-111">実装は、表示されるターゲット項目の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fa79d-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="fa79d-112">ターゲット項目には、プロセス、メモリダンプ、リモートコンピューターなどがあります。</span><span class="sxs-lookup"><span data-stu-id="fa79d-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa79d-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="fa79d-113">Requirements</span></span>  
 <span data-ttu-id="fa79d-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa79d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa79d-115">**ヘッダー:** ClrData .idl</span><span class="sxs-lookup"><span data-stu-id="fa79d-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="fa79d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa79d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa79d-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa79d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa79d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa79d-118">See also</span></span>

- [<span data-ttu-id="fa79d-119">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="fa79d-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
