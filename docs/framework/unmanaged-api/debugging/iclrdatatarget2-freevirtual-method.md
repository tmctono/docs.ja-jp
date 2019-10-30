---
title: ICLRDataTarget2::FreeVirtual メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: c084a3fcbbc02504124a511c6e136be32f408d21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112325"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="e2237-102">ICLRDataTarget2::FreeVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="e2237-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="e2237-103">ターゲットプロセスのアドレス空間で以前に割り当てられたメモリを解放するために、共通言語ランタイム (CLR) データアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2237-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2237-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2237-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2237-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2237-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="e2237-106">から解放されるメモリの開始アドレスを指定する `CLRDATA_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="e2237-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="e2237-107">から解放されるメモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="e2237-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="e2237-108">からメモリの解放を制御するフラグ。</span><span class="sxs-lookup"><span data-stu-id="e2237-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="e2237-109">Win32 `VirtualFree` 関数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2237-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2237-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2237-110">Remarks</span></span>  
 <span data-ttu-id="e2237-111">`FreeVirtual` メソッドは、Win32 `VirtualFree` 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="e2237-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="e2237-112">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="e2237-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2237-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="e2237-113">Requirements</span></span>  
 <span data-ttu-id="e2237-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2237-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2237-115">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="e2237-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e2237-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2237-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2237-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2237-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2237-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2237-118">See also</span></span>

- [<span data-ttu-id="e2237-119">ICLRDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2237-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="e2237-120">AllocVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="e2237-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
