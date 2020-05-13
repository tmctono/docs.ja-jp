---
title: ICorDebugMemoryBuffer::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1bef2e2d0e1a1cef74c7568fdd2e9b7986500488
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212608"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="9e44a-102">ICorDebugMemoryBuffer::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9e44a-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="9e44a-103">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e44a-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e44a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e44a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e44a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e44a-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="9e44a-106">[out] メモリ バッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e44a-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e44a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e44a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e44a-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e44a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e44a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e44a-109">Requirements</span></span>  
 <span data-ttu-id="9e44a-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e44a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e44a-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e44a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e44a-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e44a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e44a-113">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e44a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e44a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e44a-114">See also</span></span>

- [<span data-ttu-id="9e44a-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e44a-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="9e44a-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e44a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
