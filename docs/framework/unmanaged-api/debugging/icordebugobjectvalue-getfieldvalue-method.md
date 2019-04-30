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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8778edf9ac6e32d5dab3a53a6d9cc643a8df13b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994554"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="e68f5-102">ICorDebugObjectValue::GetFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="e68f5-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="e68f5-103">このオブジェクトの値の指定したクラスの指定したフィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e68f5-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e68f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="e68f5-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e68f5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e68f5-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="e68f5-106">[in]フィールドの値を取得する対象のクラスを表す"ICorDebugClass"オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e68f5-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="e68f5-107">[in]`mdFieldDef`フィールドを記述するメタデータを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="e68f5-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e68f5-108">[out]指定したフィールドの値を表す"ICorDebugValue"オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e68f5-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e68f5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e68f5-109">Remarks</span></span>  
 <span data-ttu-id="e68f5-110">指定された、クラス、`pClass`パラメーターに、オブジェクトの値のクラスの階層にする必要があり、フィールドはそのクラスのフィールドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68f5-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="e68f5-111">`GetFieldValue`汎用オブジェクトおよびジェネリック クラスのメソッドは成功します。</span><span class="sxs-lookup"><span data-stu-id="e68f5-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="e68f5-112">たとえば場合、MyDictionary\<V > ディクショナリから継承\<文字列、V >、オブジェクトの値の種類 MyDictionary\<int32 > を渡して、`ICorDebugClass`ディクショナリのオブジェクト\<K, V > はディクショナリのフィールドを正常に取得\<string, int32 > です。</span><span class="sxs-lookup"><span data-stu-id="e68f5-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e68f5-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e68f5-113">Requirements</span></span>  
 <span data-ttu-id="e68f5-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e68f5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e68f5-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e68f5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e68f5-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e68f5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e68f5-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e68f5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e68f5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e68f5-118">See also</span></span>
