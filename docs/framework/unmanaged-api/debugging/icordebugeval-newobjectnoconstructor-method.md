---
title: ICorDebugEval::NewObjectNoConstructor メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93fff7ec315edec8b20b4149650b27e7792fb2f1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475048"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="929f2-102">ICorDebugEval::NewObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="929f2-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="929f2-103">コンス トラクター メソッドを呼び出そうとすると、指定した型の新しいオブジェクト インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="929f2-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="929f2-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="929f2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="929f2-105">使用[icordebugeval 2::newparameterizedobjectnoconstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="929f2-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929f2-106">構文</span><span class="sxs-lookup"><span data-stu-id="929f2-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="929f2-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="929f2-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="929f2-108">[in]ICorDebugClass を表すオブジェクトをインスタンス化されるオブジェクトの型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="929f2-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929f2-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="929f2-109">Requirements</span></span>  
 <span data-ttu-id="929f2-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="929f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929f2-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="929f2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="929f2-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="929f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929f2-113">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="929f2-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929f2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="929f2-114">See also</span></span>
- [<span data-ttu-id="929f2-115">NewParameterizedObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="929f2-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
