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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c24d6e9c42a091eafbe6d4bdee2bb4e055fd8852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772040"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="a38d6-102">ICorDebugType::GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="a38d6-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="a38d6-103">1 つが存在する場合、これによって表される型の基本の型を表す、ICorDebugType へのインターフェイス ポインターを取得`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="a38d6-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="a38d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a38d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a38d6-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="a38d6-106">[out]アドレスへのポインター、`ICorDebugType`基本データ型を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a38d6-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a38d6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a38d6-107">Remarks</span></span>  
 <span data-ttu-id="a38d6-108">型の基本型の検索は、オブジェクトまたはその親クラスのすべてのフィールドの印刷などの一般的なデバッガー機能を実装するために便利です。</span><span class="sxs-lookup"><span data-stu-id="a38d6-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38d6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a38d6-109">Requirements</span></span>  
 <span data-ttu-id="a38d6-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a38d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a38d6-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a38d6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a38d6-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a38d6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a38d6-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a38d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
