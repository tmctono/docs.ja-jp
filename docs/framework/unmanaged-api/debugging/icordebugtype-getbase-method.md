---
title: ICorDebugType::GetBase メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: fc406f6e87e5b2be48c6fe7d5fc988774ac5cd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379982"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="e1638-102">ICorDebugType::GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="e1638-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="e1638-103">このによって表される型の基本型 (存在する場合) を表す、の型へのインターフェイスポインターを取得し `ICorDebugType` ます。</span><span class="sxs-lookup"><span data-stu-id="e1638-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1638-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1638-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1638-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1638-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="e1638-106">入出力基本型を表すオブジェクトのアドレスへのポインター `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="e1638-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1638-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1638-107">Remarks</span></span>  
 <span data-ttu-id="e1638-108">型の基本型を検索すると、オブジェクトまたはその親クラスのすべてのフィールドを出力するなど、一般的なデバッガー機能を実装するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="e1638-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1638-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e1638-109">Requirements</span></span>  
 <span data-ttu-id="e1638-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1638-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1638-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1638-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1638-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1638-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1638-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1638-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
