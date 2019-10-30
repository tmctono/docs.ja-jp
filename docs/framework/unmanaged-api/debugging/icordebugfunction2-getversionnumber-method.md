---
title: ICorDebugFunction2::GetVersionNumber メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 5826297d8151cf05e1ec08acbf5c9cd381d2452b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137800"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="59095-102">ICorDebugFunction2::GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="59095-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="59095-103">この関数のエディットコンティニュバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="59095-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59095-104">構文</span><span class="sxs-lookup"><span data-stu-id="59095-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59095-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59095-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="59095-106">入出力この ICorDebugFunction2 オブジェクトによって表される関数のバージョン番号である整数を指すポインターです。</span><span class="sxs-lookup"><span data-stu-id="59095-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59095-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="59095-107">Remarks</span></span>  
 <span data-ttu-id="59095-108">ランタイムは、デバッグセッション中に各モジュールに対して行われた編集の数を追跡します。</span><span class="sxs-lookup"><span data-stu-id="59095-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="59095-109">関数のバージョン番号は、関数を導入した編集の数を1つ超えています。</span><span class="sxs-lookup"><span data-stu-id="59095-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="59095-110">関数の元のバージョンは、バージョン1です。</span><span class="sxs-lookup"><span data-stu-id="59095-110">The function's original version is version 1.</span></span> <span data-ttu-id="59095-111">この値は、そのモジュールで[ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)が呼び出されるたびに、モジュールに対してインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="59095-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="59095-112">したがって、関数の本体が `ICorDebugModule2::ApplyChanges`への最初の呼び出しと3回目の呼び出しで置き換えられた場合、`GetVersionNumber` はその関数のバージョン1、2、または4を返すことがありますが、バージョン3は返されません。</span><span class="sxs-lookup"><span data-stu-id="59095-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="59095-113">(この関数にはバージョン3はありません)。</span><span class="sxs-lookup"><span data-stu-id="59095-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="59095-114">バージョン番号は、モジュールごとに個別に追跡されます。</span><span class="sxs-lookup"><span data-stu-id="59095-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="59095-115">したがって、モジュール1で4つの編集を実行し、モジュール2では何も実行しない場合、モジュール1の次の編集では、モジュール1のすべての編集された関数にバージョン番号6が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="59095-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="59095-116">同じ編集がモジュール2の場合、モジュール2の関数のバージョン番号は2になります。</span><span class="sxs-lookup"><span data-stu-id="59095-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="59095-117">`GetVersionNumber` メソッドによって取得されたバージョン番号は、 [GetCurrentVersionNumber 関数::](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)によって取得された値よりも小さくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="59095-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="59095-118">[コード:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)メソッドは、`ICorDebugFunction2::GetVersionNumber`と同じ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="59095-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59095-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="59095-119">Requirements</span></span>  
 <span data-ttu-id="59095-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59095-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59095-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59095-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59095-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59095-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59095-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59095-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
