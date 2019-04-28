---
title: ICorDebugStaticFieldSymbol::GetAddress メソッド
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e233fe78f6b2c721114f0307a8ca414625a0087e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782643"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="328cb-102">ICorDebugStaticFieldSymbol::GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="328cb-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="328cb-103">静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="328cb-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="328cb-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="328cb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="328cb-105">Parameters</span></span>  
 <span data-ttu-id="328cb-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="328cb-106">pRVA</span></span>  
 <span data-ttu-id="328cb-107">[out] 静的フィールドの相対仮想アドレス (RVA) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="328cb-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="328cb-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="328cb-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="328cb-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="328cb-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328cb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="328cb-110">Requirements</span></span>  
 <span data-ttu-id="328cb-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="328cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="328cb-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="328cb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="328cb-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="328cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="328cb-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="328cb-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328cb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="328cb-115">See also</span></span>

- [<span data-ttu-id="328cb-116">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="328cb-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="328cb-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="328cb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
