---
title: CLRDataCreateInstance 関数
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a4a8a2fc737bbf4b49ca859f0549ca7efd54a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089771"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="0df70-102">CLRDataCreateInstance 関数</span><span class="sxs-lookup"><span data-stu-id="0df70-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="0df70-103">指定したターゲット項目のインターフェイス オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0df70-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0df70-104">構文</span><span class="sxs-lookup"><span data-stu-id="0df70-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0df70-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0df70-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="0df70-106">[in]インスタンス化するインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="0df70-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="0df70-107">[in]ユーザー実装へのポインター [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)インターフェイス オブジェクトを作成する対象のターゲット項目を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0df70-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="0df70-108">[out]返されたインターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0df70-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0df70-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0df70-109">Remarks</span></span>  
 <span data-ttu-id="0df70-110">`ICLRDataTarget`オブジェクトがデバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="0df70-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="0df70-111">実装は、表されるターゲット項目の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0df70-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="0df70-112">ターゲット項目には、プロセス、メモリ ダンプ、リモート コンピューター、およびなどがあります。</span><span class="sxs-lookup"><span data-stu-id="0df70-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0df70-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="0df70-113">Requirements</span></span>  
 <span data-ttu-id="0df70-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0df70-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0df70-115">**ヘッダー:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="0df70-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="0df70-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0df70-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0df70-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0df70-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0df70-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0df70-118">See also</span></span>

- [<span data-ttu-id="0df70-119">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="0df70-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
