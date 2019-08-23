---
title: ICorDebugInstanceFieldSymbol::GetOffset メソッド
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 453f691f414050905f5d73e201ebeed79e2aaf50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910201"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="24c0a-102">ICorDebugInstanceFieldSymbol::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="24c0a-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="24c0a-103">このインスタンス フィールドの親クラスにおける、このインスタンス フィールドのオフセット (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="24c0a-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c0a-104">構文</span><span class="sxs-lookup"><span data-stu-id="24c0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24c0a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="24c0a-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="24c0a-106">このインスタンス フィールドの親クラスにおける、このフィールドのオフセットのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="24c0a-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24c0a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="24c0a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24c0a-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="24c0a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24c0a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="24c0a-109">Requirements</span></span>  
 <span data-ttu-id="24c0a-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24c0a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c0a-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="24c0a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24c0a-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="24c0a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24c0a-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c0a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c0a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="24c0a-114">See also</span></span>

- [<span data-ttu-id="24c0a-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24c0a-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="24c0a-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24c0a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
