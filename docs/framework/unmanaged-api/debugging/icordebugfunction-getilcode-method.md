---
title: ICorDebugFunction::GetILCode メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213622"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="a450f-102">ICorDebugFunction::GetILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="a450f-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="a450f-103">このオブジェクトに関連付けられている MSIL (Microsoft 中間言語) コードを表す、コードインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a450f-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a450f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a450f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a450f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a450f-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="a450f-106">入出力インスタンスへのポインター。 `ICorDebugCode` 関数が MSIL にコンパイルされなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="a450f-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a450f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a450f-107">Remarks</span></span>  
 <span data-ttu-id="a450f-108">この関数でエディットコンティニュが許可されている場合、メソッドは、 `GetILCode` 共通言語ランタイム (CLR) で、この関数の編集されたバージョンのコードに対応する MSIL コードを取得します。</span><span class="sxs-lookup"><span data-stu-id="a450f-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a450f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a450f-109">Requirements</span></span>  
 <span data-ttu-id="a450f-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a450f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a450f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a450f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a450f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a450f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a450f-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a450f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
