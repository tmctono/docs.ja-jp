---
title: ICorDebugMemoryBuffer::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0db104dbfa61b836aa01b99be45725ed4c04c798
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752779"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="d10cd-102">ICorDebugMemoryBuffer::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="d10cd-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="d10cd-103">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d10cd-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d10cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="d10cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d10cd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d10cd-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="d10cd-106">[out] メモリ バッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d10cd-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d10cd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d10cd-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d10cd-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d10cd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d10cd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d10cd-109">Requirements</span></span>  
 <span data-ttu-id="d10cd-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d10cd-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d10cd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d10cd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d10cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d10cd-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d10cd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10cd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d10cd-114">See also</span></span>

- [<span data-ttu-id="d10cd-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d10cd-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d10cd-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d10cd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
