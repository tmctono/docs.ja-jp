---
title: ICorDebugInstanceFieldSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946374"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="9c990-102">ICorDebugInstanceFieldSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9c990-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="9c990-103">インスタンス フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9c990-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c990-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c990-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c990-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c990-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9c990-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9c990-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c990-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c990-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c990-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c990-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c990-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c990-109">Requirements</span></span>  
 <span data-ttu-id="9c990-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c990-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c990-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c990-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c990-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c990-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c990-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c990-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c990-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c990-114">See also</span></span>

- [<span data-ttu-id="9c990-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c990-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="9c990-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c990-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
