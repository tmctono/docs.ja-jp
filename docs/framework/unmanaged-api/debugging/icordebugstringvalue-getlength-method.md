---
title: ICorDebugStringValue::GetLength メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
ms.openlocfilehash: 945e4ac88634c9103a722a180a4fe92a554ca53b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378895"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="042dd-102">ICorDebugStringValue::GetLength メソッド</span><span class="sxs-lookup"><span data-stu-id="042dd-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="042dd-103">このによって参照される文字列の文字数を取得します。</span><span class="sxs-lookup"><span data-stu-id="042dd-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="042dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="042dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="042dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="042dd-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="042dd-106">入出力このオブジェクトによって参照される文字列の長さを指定する値へのポインター `ICorDebugStringValue` 。</span><span class="sxs-lookup"><span data-stu-id="042dd-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="042dd-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="042dd-107">Requirements</span></span>  
 <span data-ttu-id="042dd-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="042dd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="042dd-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="042dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="042dd-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="042dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="042dd-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="042dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
