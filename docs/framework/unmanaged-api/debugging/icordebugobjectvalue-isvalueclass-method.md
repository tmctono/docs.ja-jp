---
title: ICorDebugObjectValue::IsValueClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e32211e6ab16fb5e4e2c624dbad3af5fd6b09f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994527"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="d54cc-102">ICorDebugObjectValue::IsValueClass メソッド</span><span class="sxs-lookup"><span data-stu-id="d54cc-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="d54cc-103">このオブジェクトの値が値型かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d54cc-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d54cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d54cc-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d54cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d54cc-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="d54cc-106">[out]ブール値へのポインター`true`この"ICorDebugObjectValue"で表される、オブジェクトの値が参照型ではなく、値型の場合、それ以外の場合`pbIsValueClass`は`false`します。</span><span class="sxs-lookup"><span data-stu-id="d54cc-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d54cc-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="d54cc-107">Requirements</span></span>  
 <span data-ttu-id="d54cc-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d54cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d54cc-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d54cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d54cc-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d54cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d54cc-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d54cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54cc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d54cc-112">See also</span></span>
