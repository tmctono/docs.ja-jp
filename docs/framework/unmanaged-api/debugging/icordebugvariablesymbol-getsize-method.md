---
title: Icordebugvariablesymbol::getsize メソッド
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027b3f773ff0ed0ca7bf9d193f97a3b060ea8494
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211843"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="66db7-102">Icordebugvariablesymbol::getsize メソッド</span><span class="sxs-lookup"><span data-stu-id="66db7-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="66db7-103">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="66db7-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66db7-104">構文</span><span class="sxs-lookup"><span data-stu-id="66db7-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66db7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66db7-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="66db7-106">変数のサイズが格納されている 32 ビットの符号なし整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="66db7-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66db7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="66db7-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66db7-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="66db7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66db7-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="66db7-109">Requirements</span></span>  
 <span data-ttu-id="66db7-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66db7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66db7-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66db7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66db7-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66db7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66db7-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66db7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66db7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="66db7-114">See also</span></span>

- [<span data-ttu-id="66db7-115">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66db7-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="66db7-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66db7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
