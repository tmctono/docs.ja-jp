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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207589"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="e6715-102">ICorDebugObjectValue::GetFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="e6715-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="e6715-103">このオブジェクト値について、指定したクラスの指定したフィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6715-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6715-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6715-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6715-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6715-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="e6715-106">からフィールド値を取得する対象のクラスを表す "表示クラス" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6715-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="e6715-107">から`mdFieldDef`フィールドを記述するメタデータを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="e6715-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e6715-108">入出力指定したフィールドの値を表す "ICorDebugValue" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6715-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6715-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6715-109">Remarks</span></span>  
 <span data-ttu-id="e6715-110">パラメーターで指定されたクラスは、 `pClass` オブジェクト値のクラスの階層内に存在する必要があり、フィールドはそのクラスのフィールドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6715-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="e6715-111">`GetFieldValue`ジェネリックオブジェクトとジェネリッククラスでは、メソッドは引き続き成功します。</span><span class="sxs-lookup"><span data-stu-id="e6715-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="e6715-112">たとえば、MyDictionary \< v> \< がディクショナリ文字列 v> から継承し、オブジェクト値が mydictionary int32> 型である場合、 \< `ICorDebugClass` ディクショナリ K のオブジェクトを渡すと、 \< V> は dictionary 文字列, int32> のフィールドを正常に取得し \< ます。</span><span class="sxs-lookup"><span data-stu-id="e6715-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6715-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6715-113">Requirements</span></span>  
 <span data-ttu-id="e6715-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6715-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6715-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6715-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6715-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6715-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6715-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6715-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6715-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6715-118">See also</span></span>
