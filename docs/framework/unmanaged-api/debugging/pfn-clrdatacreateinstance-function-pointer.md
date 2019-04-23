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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff2ddb1e98f3455c6915acf8149f528176228425
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177984"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="36a8c-102">PFN_CLRDataCreateInstance 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="36a8c-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="36a8c-103">指定したターゲット項目のインターフェイス オブジェクトを作成する関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="36a8c-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a8c-104">構文</span><span class="sxs-lookup"><span data-stu-id="36a8c-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36a8c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36a8c-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="36a8c-106">[in]インスタンス化するインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="36a8c-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="36a8c-107">[in]ユーザー実装へのポインター [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)インターフェイス オブジェクトを作成する対象のターゲット項目を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="36a8c-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="36a8c-108">[out]返されたインターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="36a8c-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36a8c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="36a8c-109">Remarks</span></span>  
 <span data-ttu-id="36a8c-110">`ICLRDataTarget`オブジェクトがデバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="36a8c-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="36a8c-111">実装は、表されるターゲット項目の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="36a8c-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="36a8c-112">ターゲット項目には、プロセス、メモリ ダンプ、リモート コンピューター、およびなどがあります。</span><span class="sxs-lookup"><span data-stu-id="36a8c-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36a8c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="36a8c-113">Requirements</span></span>  
 <span data-ttu-id="36a8c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a8c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36a8c-115">**ヘッダー:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="36a8c-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="36a8c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36a8c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36a8c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36a8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a8c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="36a8c-118">See also</span></span>

- [<span data-ttu-id="36a8c-119">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="36a8c-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
