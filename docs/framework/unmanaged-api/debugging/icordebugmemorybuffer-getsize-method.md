---
title: ICorDebugMemoryBuffer::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d687f2bbd3c20564368d4246961b56382ea14cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099678"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="2b80c-102">ICorDebugMemoryBuffer::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="2b80c-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="2b80c-103">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="2b80c-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b80c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b80c-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b80c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b80c-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="2b80c-106">[out] メモリ バッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2b80c-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b80c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b80c-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b80c-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b80c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b80c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b80c-109">Requirements</span></span>  
 <span data-ttu-id="2b80c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b80c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b80c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b80c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b80c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b80c-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2b80c-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="2b80c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b80c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b80c-114">See also</span></span>

- [<span data-ttu-id="2b80c-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b80c-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="2b80c-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b80c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
