---
title: ICorDebugLoadedModule::GetName メソッド
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bf09c01d24315c3f239911326f1844a0b2cc101
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946264"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="f4efe-102">ICorDebugLoadedModule::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="f4efe-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="f4efe-103">読み込まれたモジュールの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="f4efe-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4efe-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4efe-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4efe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4efe-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f4efe-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="f4efe-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f4efe-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f4efe-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f4efe-108">[out] 読み込まれたモジュールの名前が含まれている文字配列。</span><span class="sxs-lookup"><span data-stu-id="f4efe-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4efe-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4efe-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4efe-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4efe-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4efe-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4efe-111">Requirements</span></span>  
 <span data-ttu-id="f4efe-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4efe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4efe-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4efe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4efe-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4efe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4efe-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4efe-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4efe-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4efe-116">See also</span></span>

- [<span data-ttu-id="f4efe-117">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4efe-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="f4efe-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4efe-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
