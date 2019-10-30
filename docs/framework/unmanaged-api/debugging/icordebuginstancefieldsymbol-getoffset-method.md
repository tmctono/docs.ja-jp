---
title: 'GetOffset Instancefieldsymbol:: メソッド'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 3886e29a1c2fd44fbe50d1eef722f99da7abdbe5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139017"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="bcebc-102">GetOffset Instancefieldsymbol:: メソッド</span><span class="sxs-lookup"><span data-stu-id="bcebc-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="bcebc-103">このインスタンス フィールドの親クラスにおける、このインスタンス フィールドのオフセット (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="bcebc-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcebc-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcebc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcebc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcebc-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="bcebc-106">このインスタンス フィールドの親クラスにおける、このフィールドのオフセットのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bcebc-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcebc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcebc-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcebc-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcebc-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcebc-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="bcebc-109">Requirements</span></span>  
 <span data-ttu-id="bcebc-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcebc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcebc-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcebc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcebc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcebc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcebc-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcebc-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcebc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcebc-114">See also</span></span>

- [<span data-ttu-id="bcebc-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcebc-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="bcebc-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcebc-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
