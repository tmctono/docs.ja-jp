---
title: ICorDebugLoadedModule::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4601261971cce32b6d6d9ee7377f725a85103a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183470"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="1b571-102">ICorDebugLoadedModule::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1b571-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="1b571-103">読み込まれたモジュールのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="1b571-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b571-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b571-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b571-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b571-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="1b571-106">[out] 読み込まれたモジュールのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b571-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b571-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b571-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b571-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b571-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b571-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1b571-109">Requirements</span></span>  
 <span data-ttu-id="1b571-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b571-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b571-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b571-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b571-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b571-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1b571-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1b571-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b571-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b571-114">See also</span></span>

- [<span data-ttu-id="1b571-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b571-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="1b571-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b571-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
