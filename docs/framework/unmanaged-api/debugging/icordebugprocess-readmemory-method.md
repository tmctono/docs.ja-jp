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
ms.openlocfilehash: dca2a4e5ee869346108137a8ba01ab8855756725
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792553"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="fcd0b-102">ICorDebugProcess::ReadMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="fcd0b-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="fcd0b-103">このプロセスの指定したメモリ領域を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcd0b-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcd0b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="fcd0b-106">から読み取るメモリのベースアドレスを指定する `CORDB_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="fcd0b-107">からメモリから読み取るバイト数。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="fcd0b-108">入出力メモリの内容を受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="fcd0b-109">入出力指定したバッファーに転送されたバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd0b-110">コメント</span><span class="sxs-lookup"><span data-stu-id="fcd0b-110">Remarks</span></span>  
 <span data-ttu-id="fcd0b-111">`ReadMemory` メソッドは、主に、デバッグ対象のアンマネージ部分で使用されているメモリ領域を検査するために相互運用機能デバッグによって使用されることを意図しています。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="fcd0b-112">このメソッドを使用して、Microsoft 中間言語 (MSIL) コードとネイティブの JIT コンパイルコードを読み取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="fcd0b-113">マネージブレークポイントは、`buffer` パラメーターで返されたデータから削除されます。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="fcd0b-114">[ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)によって設定されたネイティブブレークポイントに対して調整は行われません。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="fcd0b-115">プロセスメモリのキャッシュは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd0b-116">要件</span><span class="sxs-lookup"><span data-stu-id="fcd0b-116">Requirements</span></span>  
 <span data-ttu-id="fcd0b-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd0b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd0b-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcd0b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcd0b-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd0b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd0b-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd0b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
