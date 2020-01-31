---
title: ICorDebugLoadedModule::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788463"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="00461-102">ICorDebugLoadedModule::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="00461-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="00461-103">読み込まれたモジュールのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="00461-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00461-104">構文</span><span class="sxs-lookup"><span data-stu-id="00461-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00461-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00461-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="00461-106">[out] 読み込まれたモジュールのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="00461-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00461-107">コメント</span><span class="sxs-lookup"><span data-stu-id="00461-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00461-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="00461-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00461-109">要件</span><span class="sxs-lookup"><span data-stu-id="00461-109">Requirements</span></span>  
 <span data-ttu-id="00461-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00461-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00461-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00461-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00461-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00461-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00461-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00461-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00461-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="00461-114">See also</span></span>

- [<span data-ttu-id="00461-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00461-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="00461-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00461-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
