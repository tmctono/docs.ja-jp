---
title: Icordebugmemorybuffer::getstartaddress メソッド
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9208d07b697c3bb8a99e13582eda70dcb8dd826b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752774"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="a33e9-102">Icordebugmemorybuffer::getstartaddress メソッド</span><span class="sxs-lookup"><span data-stu-id="a33e9-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="a33e9-103">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a33e9-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="a33e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a33e9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a33e9-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a33e9-106">[out] メモリ バッファーの開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a33e9-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a33e9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a33e9-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a33e9-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a33e9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a33e9-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a33e9-109">Requirements</span></span>  
 <span data-ttu-id="a33e9-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a33e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a33e9-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a33e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a33e9-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a33e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a33e9-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a33e9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33e9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a33e9-114">See also</span></span>

- [<span data-ttu-id="a33e9-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a33e9-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a33e9-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a33e9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
