---
title: 'ICorDebugVariableSymbol:: GetSize メソッド'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 782073968030d3dcdbbe49e0ed7732fe15c4a3bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968174"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="a8fdf-102">ICorDebugVariableSymbol:: GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="a8fdf-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="a8fdf-103">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8fdf-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8fdf-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8fdf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8fdf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8fdf-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="a8fdf-106">変数のサイズが格納されている 32 ビットの符号なし整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8fdf-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8fdf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8fdf-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8fdf-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8fdf-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8fdf-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8fdf-109">Requirements</span></span>  
 <span data-ttu-id="a8fdf-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8fdf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8fdf-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a8fdf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8fdf-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a8fdf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8fdf-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8fdf-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fdf-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8fdf-114">See also</span></span>

- [<span data-ttu-id="a8fdf-115">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8fdf-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="a8fdf-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8fdf-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
