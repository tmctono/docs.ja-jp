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
ms.openlocfilehash: 71836108dbd0ce01a64b4d9ac773c28d385dfd7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099685"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="353b4-102">CLRDataCreateInstance 関数</span><span class="sxs-lookup"><span data-stu-id="353b4-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="353b4-103">指定したターゲット項目のインターフェイスオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="353b4-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="353b4-104">構文</span><span class="sxs-lookup"><span data-stu-id="353b4-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="353b4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="353b4-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="353b4-106">からインスタンス化するインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="353b4-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="353b4-107">からインターフェイスオブジェクトの作成対象となる項目を表す、ユーザーによって実装された[ICLRDataTarget](iclrdatatarget-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="353b4-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="353b4-108">入出力返されたインターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="353b4-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="353b4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="353b4-109">Remarks</span></span>  
 <span data-ttu-id="353b4-110">`ICLRDataTarget` オブジェクトは、デバッグアプリケーションのライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="353b4-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="353b4-111">実装は、表示されるターゲット項目の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="353b4-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="353b4-112">ターゲット項目には、プロセス、メモリダンプ、リモートコンピューターなどがあります。</span><span class="sxs-lookup"><span data-stu-id="353b4-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="353b4-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="353b4-113">Requirements</span></span>  
 <span data-ttu-id="353b4-114">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="353b4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="353b4-115">**ヘッダー:** ClrData .idl</span><span class="sxs-lookup"><span data-stu-id="353b4-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="353b4-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="353b4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="353b4-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="353b4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353b4-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="353b4-118">See also</span></span>

- [<span data-ttu-id="353b4-119">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="353b4-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
