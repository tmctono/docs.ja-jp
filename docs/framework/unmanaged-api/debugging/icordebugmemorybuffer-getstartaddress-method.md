---
title: Icordebugmemorybuffer::getstartaddress メソッド
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136982"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="fc777-102">Icordebugmemorybuffer::getstartaddress メソッド</span><span class="sxs-lookup"><span data-stu-id="fc777-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="fc777-103">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fc777-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc777-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc777-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc777-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc777-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="fc777-106">[out] メモリ バッファーの開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fc777-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc777-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc777-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="fc777-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc777-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc777-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc777-109">Requirements</span></span>  
 <span data-ttu-id="fc777-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc777-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc777-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc777-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc777-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc777-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fc777-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="fc777-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc777-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc777-114">See also</span></span>

- [<span data-ttu-id="fc777-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc777-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="fc777-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc777-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
