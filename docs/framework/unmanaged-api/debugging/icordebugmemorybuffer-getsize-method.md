---
title: 'GetSize Memorybuffer:: メソッド'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1693860abe99884ee443be0666dfb6b485a219a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128003"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="75165-102">GetSize Memorybuffer:: メソッド</span><span class="sxs-lookup"><span data-stu-id="75165-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="75165-103">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="75165-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75165-104">構文</span><span class="sxs-lookup"><span data-stu-id="75165-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75165-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75165-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="75165-106">[out] メモリ バッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75165-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75165-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="75165-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75165-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="75165-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75165-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="75165-109">Requirements</span></span>  
 <span data-ttu-id="75165-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75165-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75165-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75165-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75165-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75165-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75165-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75165-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75165-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="75165-114">See also</span></span>

- [<span data-ttu-id="75165-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75165-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="75165-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75165-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
