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
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178663"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="5c280-102">ICorDebugProcess::ReadMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="5c280-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="5c280-103">このプロセスのメモリの指定された領域を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5c280-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c280-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c280-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c280-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c280-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5c280-106">[in]読`CORDB_ADDRESS`み取るメモリのベース アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="5c280-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="5c280-107">[in]メモリから読み取るバイト数。</span><span class="sxs-lookup"><span data-stu-id="5c280-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5c280-108">[アウト]メモリの内容を受け取るバッファ。</span><span class="sxs-lookup"><span data-stu-id="5c280-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="5c280-109">[アウト]指定したバッファーに転送されるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5c280-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c280-110">解説</span><span class="sxs-lookup"><span data-stu-id="5c280-110">Remarks</span></span>  
 <span data-ttu-id="5c280-111">この`ReadMemory`メソッドは、主に、デバッグ対象のアンマネージ部分で使用されているメモリ領域を調べるための相互運用機能デバッグで使用されることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="5c280-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="5c280-112">このメソッドは、Microsoft 中間言語 (MSIL) コードおよびネイティブ JIT コンパイルコードを読み取るためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c280-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="5c280-113">マネージ ブレークポイントは、`buffer`パラメーターで返されるデータから削除されます。</span><span class="sxs-lookup"><span data-stu-id="5c280-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="5c280-114">[ICorDebugProcess2](icordebugprocess2-setunmanagedbreakpoint-method.md)によって設定されたネイティブ ブレークポイントに対する調整は行いません。</span><span class="sxs-lookup"><span data-stu-id="5c280-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="5c280-115">プロセス メモリのキャッシュは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5c280-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c280-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c280-116">Requirements</span></span>  
 <span data-ttu-id="5c280-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c280-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c280-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c280-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c280-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c280-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c280-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c280-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
