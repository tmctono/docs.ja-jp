---
title: ICorDebugObjectValue::GetFieldValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095889"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="b96f0-102">ICorDebugObjectValue::GetFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="b96f0-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="b96f0-103">このオブジェクト値について、指定したクラスの指定したフィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b96f0-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b96f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b96f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b96f0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b96f0-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="b96f0-106">からフィールド値を取得する対象のクラスを表す "表示クラス" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b96f0-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="b96f0-107">からフィールドを記述するメタデータを参照する `mdFieldDef` トークン。</span><span class="sxs-lookup"><span data-stu-id="b96f0-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b96f0-108">入出力指定したフィールドの値を表す "ICorDebugValue" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b96f0-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b96f0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b96f0-109">Remarks</span></span>  
 <span data-ttu-id="b96f0-110">`pClass` パラメーターで指定されたクラスは、オブジェクト値のクラスの階層内に存在する必要があり、フィールドはそのクラスのフィールドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b96f0-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="b96f0-111">`GetFieldValue` メソッドは、ジェネリックオブジェクトおよびジェネリッククラスでも成功します。</span><span class="sxs-lookup"><span data-stu-id="b96f0-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="b96f0-112">たとえば、MyDictionary\<V > が Dictionary\<string, V > から継承され、オブジェクト値が MyDictionary\<int32 > 型である場合、Dictionary `ICorDebugClass` K の\<オブジェクトを渡すと、V > は次のフィールドを正常に取得します。Dictionary\<string、int32 >。</span><span class="sxs-lookup"><span data-stu-id="b96f0-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b96f0-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="b96f0-113">Requirements</span></span>  
 <span data-ttu-id="b96f0-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b96f0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b96f0-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b96f0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b96f0-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b96f0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b96f0-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b96f0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96f0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b96f0-118">See also</span></span>
