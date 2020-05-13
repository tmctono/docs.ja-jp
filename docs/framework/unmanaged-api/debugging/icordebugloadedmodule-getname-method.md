---
title: ICorDebugLoadedModule::GetName メソッド
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 4a0c4e99f23dc949b0bbaa8bbda35cff1537cf3c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209865"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="b2d37-102">ICorDebugLoadedModule::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d37-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="b2d37-103">読み込まれたモジュールの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2d37-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d37-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2d37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2d37-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2d37-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b2d37-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="b2d37-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b2d37-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2d37-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="b2d37-108">[out] 読み込まれたモジュールの名前が含まれている文字配列。</span><span class="sxs-lookup"><span data-stu-id="b2d37-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2d37-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2d37-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2d37-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2d37-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2d37-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2d37-111">Requirements</span></span>  
 <span data-ttu-id="b2d37-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2d37-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2d37-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2d37-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2d37-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2d37-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2d37-115">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2d37-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d37-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2d37-116">See also</span></span>

- [<span data-ttu-id="b2d37-117">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d37-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="b2d37-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d37-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
