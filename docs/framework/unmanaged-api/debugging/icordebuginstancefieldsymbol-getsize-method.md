---
title: ICorDebugInstanceFieldSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ff0ddc266ef9a3f5fabf56f43f1eba2c74e3a8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910176"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="e576e-102">ICorDebugInstanceFieldSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="e576e-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="e576e-103">インスタンス フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e576e-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e576e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e576e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e576e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e576e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="e576e-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e576e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e576e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e576e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e576e-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e576e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e576e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e576e-109">Requirements</span></span>  
 <span data-ttu-id="e576e-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e576e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e576e-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e576e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e576e-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="e576e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e576e-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e576e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e576e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e576e-114">See also</span></span>

- [<span data-ttu-id="e576e-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e576e-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="e576e-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e576e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
