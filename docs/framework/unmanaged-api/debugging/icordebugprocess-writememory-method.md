---
title: ICorDebugProcess::WriteMemory メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930300"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="9bfd6-102">ICorDebugProcess::WriteMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="9bfd6-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="9bfd6-103">このプロセスでメモリの領域にデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bfd6-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bfd6-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bfd6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9bfd6-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9bfd6-106">[in]A`CORDB_ADDRESS`データ メモリ領域のベース アドレスは、値が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="9bfd6-107">データ転送が発生する前に、システムは、ベース アドレスで始まる、指定したサイズのメモリ領域が書き込み用にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="9bfd6-108">アクセスできない場合、メソッドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="9bfd6-109">[in]メモリ領域に書き込まれるバイト数。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9bfd6-110">[in]書き込むデータを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="9bfd6-111">[out]このプロセスのメモリ領域に書き込まれたバイト数を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="9bfd6-112">場合`written`が null の場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bfd6-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="9bfd6-113">Remarks</span></span>  
 <span data-ttu-id="9bfd6-114">データは、ブレークポイントの背後に自動的に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="9bfd6-115">.NET framework version 2.0 では、ネイティブ デバッガーは、命令ストリームにブレークポイントを挿入するのにこのメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="9bfd6-116">使用[icordebugprocess 2::setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="9bfd6-117">`WriteMemory`メソッドは、マネージ コードの外側でのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="9bfd6-118">このメソッドは、誤って使用すると、ランタイムを破壊できます。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bfd6-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="9bfd6-119">Requirements</span></span>  
 <span data-ttu-id="9bfd6-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bfd6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bfd6-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bfd6-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bfd6-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bfd6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bfd6-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bfd6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
