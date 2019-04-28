---
title: ICorDebugStaticFieldSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9baa3632b6ede9ce45f34302611710344ed33761
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782604"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="9c5ad-102">ICorDebugStaticFieldSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9c5ad-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="9c5ad-103">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9c5ad-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c5ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c5ad-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c5ad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c5ad-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9c5ad-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9c5ad-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c5ad-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c5ad-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c5ad-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c5ad-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c5ad-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c5ad-109">Requirements</span></span>  
 <span data-ttu-id="9c5ad-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c5ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c5ad-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c5ad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c5ad-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c5ad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c5ad-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c5ad-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5ad-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c5ad-114">See also</span></span>

- [<span data-ttu-id="9c5ad-115">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c5ad-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9c5ad-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c5ad-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
