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
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179363"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="b5afb-102">CLRDataCreateInstance 関数</span><span class="sxs-lookup"><span data-stu-id="b5afb-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="b5afb-103">指定したターゲット項目のインターフェイス オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5afb-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5afb-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5afb-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5afb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5afb-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="b5afb-106">[in]インスタンス化されるインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="b5afb-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="b5afb-107">[in]インターフェイス オブジェクトを作成する対象の項目を表す、ユーザーが実装する[ICLRDataTarget](iclrdatatarget-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5afb-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="b5afb-108">[アウト]返されたインターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5afb-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5afb-109">解説</span><span class="sxs-lookup"><span data-stu-id="b5afb-109">Remarks</span></span>  
 <span data-ttu-id="b5afb-110">オブジェクト`ICLRDataTarget`は、デバッグ アプリケーションのライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="b5afb-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="b5afb-111">実装は、表されるターゲット項目の型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b5afb-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="b5afb-112">ターゲット項目は、プロセス、メモリ ダンプ、リモート コンピューターなどです。</span><span class="sxs-lookup"><span data-stu-id="b5afb-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5afb-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b5afb-113">Requirements</span></span>  
 <span data-ttu-id="b5afb-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5afb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5afb-115">**ヘッダー:** を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5afb-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="b5afb-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5afb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5afb-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5afb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5afb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5afb-118">See also</span></span>

- [<span data-ttu-id="b5afb-119">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="b5afb-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
