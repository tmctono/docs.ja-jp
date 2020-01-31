---
title: ICorDebugType::GetType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791240"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="5097b-102">ICorDebugType::GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="5097b-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="5097b-103">このテキスト型で表される共通言語ランタイム (CLR) <xref:System.Type> のネイティブ型を記述する CorElementType 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5097b-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5097b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5097b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5097b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5097b-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="5097b-106">入出力この `ICorDebugType` が表す CLR <xref:System.Type> を示す `CorElementType` 列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5097b-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5097b-107">コメント</span><span class="sxs-lookup"><span data-stu-id="5097b-107">Remarks</span></span>  
 <span data-ttu-id="5097b-108">`ty` の値が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の場合、ジェネリック型のインスタンス型を取得するために、の型[:: GetClass](icordebugtype-getclass-method.md)メソッドを呼び出すことができます。それ以外の場合は、`ICorDebugType::GetClass`を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="5097b-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5097b-109">要件</span><span class="sxs-lookup"><span data-stu-id="5097b-109">Requirements</span></span>  
 <span data-ttu-id="5097b-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5097b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5097b-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5097b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5097b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5097b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5097b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5097b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
