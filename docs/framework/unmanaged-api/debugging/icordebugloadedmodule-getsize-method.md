---
title: ICorDebugLoadedModule::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3067cdee1d3a5df0ad5594bce581139431fd1846
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936872"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="e2495-102">ICorDebugLoadedModule::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="e2495-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="e2495-103">読み込まれたモジュールのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e2495-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2495-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2495-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2495-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2495-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="e2495-106">[out] 読み込まれたモジュールのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e2495-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2495-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2495-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2495-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2495-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2495-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e2495-109">Requirements</span></span>  
 <span data-ttu-id="e2495-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2495-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2495-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e2495-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2495-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="e2495-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2495-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2495-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2495-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2495-114">See also</span></span>

- [<span data-ttu-id="e2495-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2495-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="e2495-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2495-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
