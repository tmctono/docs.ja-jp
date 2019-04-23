---
title: ICorDebugStaticFieldSymbol::GetAddress メソッド
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e233fe78f6b2c721114f0307a8ca414625a0087e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160421"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="93c0b-102">ICorDebugStaticFieldSymbol::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="93c0b-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="93c0b-103">静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="93c0b-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="93c0b-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93c0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93c0b-105">Parameters</span></span>  
 <span data-ttu-id="93c0b-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="93c0b-106">pRVA</span></span>  
 <span data-ttu-id="93c0b-107">[out] 静的フィールドの相対仮想アドレス (RVA) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="93c0b-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93c0b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="93c0b-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93c0b-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="93c0b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93c0b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="93c0b-110">Requirements</span></span>  
 <span data-ttu-id="93c0b-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93c0b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93c0b-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93c0b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93c0b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93c0b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93c0b-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93c0b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c0b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="93c0b-115">See also</span></span>

- [<span data-ttu-id="93c0b-116">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93c0b-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="93c0b-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93c0b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
