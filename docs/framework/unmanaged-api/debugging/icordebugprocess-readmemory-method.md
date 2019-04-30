---
title: ICorDebugProcess::ReadMemory メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 218279684304b766a9bf009f5891ac4910254a3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994384"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="a2f2f-102">ICorDebugProcess::ReadMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="a2f2f-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="a2f2f-103">このプロセスのメモリの指定された領域を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2f2f-104">Syntax</span></span>  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2f2f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2f2f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a2f2f-106">[in]A`CORDB_ADDRESS`読み取られるメモリのベース アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="a2f2f-107">[in]メモリから読み取られるバイト数。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a2f2f-108">[out]メモリの内容を受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="a2f2f-109">[out]バイト数へのポインターは、指定されたバッファーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2f2f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2f2f-110">Remarks</span></span>  
 <span data-ttu-id="a2f2f-111">`ReadMemory`メソッドは主にデバッグ対象のアンマネージ部分で使用されているメモリ領域を検査する相互運用機能デバッグで使用されるものです。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="a2f2f-112">このメソッドは、Microsoft intermediate language (MSIL) コードとネイティブ JIT コンパイル コードの読み取りにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="a2f2f-113">返されるデータから管理対象のブレークポイントは削除されます、`buffer`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="a2f2f-114">によってネイティブのブレークポイントの設定の調整は行われません[icordebugprocess 2::setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="a2f2f-115">プロセス メモリのキャッシュは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f2f-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2f2f-116">Requirements</span></span>  
 <span data-ttu-id="a2f2f-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2f2f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f2f-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2f2f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2f2f-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2f2f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2f2f-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f2f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
