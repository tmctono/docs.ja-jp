---
title: ICorDebugFunction::GetCurrentVersionNumber メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212907"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="90fce-102">ICorDebugFunction::GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="90fce-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="90fce-103">このオブジェクトによって表される関数に対して行われた最新の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="90fce-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90fce-104">構文</span><span class="sxs-lookup"><span data-stu-id="90fce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90fce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90fce-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="90fce-106">入出力この関数に対して行われた最新の編集のバージョン番号を表す整数値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="90fce-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90fce-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="90fce-107">Remarks</span></span>  
 <span data-ttu-id="90fce-108">この関数に対して行われた最新の編集のバージョン番号が、関数自体のバージョン番号よりも大きい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90fce-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="90fce-109">[ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md)メソッドまたは[Code:: GetVersionNumber](icordebugcode-getversionnumber-method.md)メソッドを使用して、関数のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="90fce-109">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90fce-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="90fce-110">Requirements</span></span>  
 <span data-ttu-id="90fce-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90fce-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90fce-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90fce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90fce-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90fce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90fce-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90fce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
