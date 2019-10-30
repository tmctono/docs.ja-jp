---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137279"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="c9aa7-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="c9aa7-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="c9aa7-103">引数またはローカル変数の値を取得します。この値は、このネイティブフレームについて、指定したレジスタとメモリ位置にそれぞれ、下位ワードと上位ワードが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9aa7-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9aa7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9aa7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9aa7-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="c9aa7-106">から値の上位ワードを格納しているメモリ位置を指定する `CORDB_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="c9aa7-107">から値の下位ワードを含むレジスタを指定する "CorDebugRegister" 列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c9aa7-108">から`pvSigBlob` パラメーターによって参照されるバイナリメタデータシグネチャのサイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c9aa7-109">から値の型のバイナリメタデータシグネチャを指す `PCCOR_SIGNATURE` 値。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c9aa7-110">入出力指定されたレジスタおよびメモリ位置に格納されている取得値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9aa7-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="c9aa7-111">Requirements</span></span>  
 <span data-ttu-id="c9aa7-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9aa7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9aa7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9aa7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9aa7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9aa7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9aa7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9aa7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9aa7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9aa7-116">See also</span></span>
