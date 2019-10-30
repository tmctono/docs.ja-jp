---
title: ICLRDataTarget::SetTLSValue メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 1425d48bb18d4161a1c96239b76b8315ae258705
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112777"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="00666-102">ICLRDataTarget::SetTLSValue メソッド</span><span class="sxs-lookup"><span data-stu-id="00666-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="00666-103">ターゲットプロセス内の指定したスレッドのスレッドローカルストレージ (TLS) の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="00666-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="00666-104">このメソッドは、共通言語ランタイム (CLR) データアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="00666-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00666-105">構文</span><span class="sxs-lookup"><span data-stu-id="00666-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00666-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00666-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="00666-107">からターゲットプロセス内のスレッドのオペレーティングシステム識別子。</span><span class="sxs-lookup"><span data-stu-id="00666-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="00666-108">から位置のインデックス。</span><span class="sxs-lookup"><span data-stu-id="00666-108">[in] The index of the location.</span></span> <span data-ttu-id="00666-109">この値は、指定されたスレッドのローカルストア内の有効なインデックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="00666-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="00666-110">から指定した TLS の場所に配置する値を指定する `CLRDATA_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="00666-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00666-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="00666-111">Remarks</span></span>  
 <span data-ttu-id="00666-112">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="00666-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00666-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="00666-113">Requirements</span></span>  
 <span data-ttu-id="00666-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00666-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00666-115">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="00666-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="00666-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00666-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00666-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00666-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00666-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="00666-118">See also</span></span>

- [<span data-ttu-id="00666-119">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00666-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
