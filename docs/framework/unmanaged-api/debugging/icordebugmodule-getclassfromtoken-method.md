---
title: ICorDebugModule::GetClassFromToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: f8a56dcf03748c6582bce07fc379113c5cdddd11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212606"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="0326a-102">ICorDebugModule::GetClassFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="0326a-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="0326a-103">メタデータトークンによって指定されたクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0326a-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0326a-104">構文</span><span class="sxs-lookup"><span data-stu-id="0326a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0326a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0326a-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="0326a-106">から`mdTypeDef`クラスのメタデータを参照するメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="0326a-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="0326a-107">入出力クラスを表す、のクラスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0326a-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0326a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="0326a-108">Requirements</span></span>  
 <span data-ttu-id="0326a-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0326a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0326a-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0326a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0326a-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0326a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0326a-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0326a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
