---
title: ICorDebugMemoryBuffer::GetStartAddress メソッド
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f2b09c847a6bf577b78c8155f85f07b93877fbe9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793167"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="d0a27-102">ICorDebugMemoryBuffer::GetStartAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="d0a27-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="d0a27-103">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0a27-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a27-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0a27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0a27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0a27-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d0a27-106">[out] メモリ バッファーの開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d0a27-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0a27-107">コメント</span><span class="sxs-lookup"><span data-stu-id="d0a27-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="d0a27-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0a27-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0a27-109">要件</span><span class="sxs-lookup"><span data-stu-id="d0a27-109">Requirements</span></span>  
 <span data-ttu-id="d0a27-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0a27-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0a27-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0a27-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0a27-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0a27-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0a27-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0a27-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a27-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0a27-114">See also</span></span>

- [<span data-ttu-id="d0a27-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0a27-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d0a27-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0a27-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
