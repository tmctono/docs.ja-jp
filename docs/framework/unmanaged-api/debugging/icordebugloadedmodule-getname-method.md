---
title: ICorDebugLoadedModule::GetName メソッド
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b3889829ced876b23ea6632f35f4da6beffdca
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759916"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="799a5-102">ICorDebugLoadedModule::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="799a5-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="799a5-103">読み込まれたモジュールの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="799a5-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="799a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="799a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="799a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="799a5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="799a5-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="799a5-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="799a5-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="799a5-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="799a5-108">[out] 読み込まれたモジュールの名前が含まれている文字配列。</span><span class="sxs-lookup"><span data-stu-id="799a5-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="799a5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="799a5-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="799a5-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="799a5-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="799a5-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="799a5-111">Requirements</span></span>  
 <span data-ttu-id="799a5-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="799a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="799a5-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="799a5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="799a5-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="799a5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="799a5-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="799a5-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799a5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="799a5-116">See also</span></span>

- [<span data-ttu-id="799a5-117">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="799a5-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="799a5-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="799a5-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
