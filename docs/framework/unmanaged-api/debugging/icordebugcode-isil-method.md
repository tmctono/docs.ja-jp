---
title: ICorDebugCode::IsIL メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a82606d90444c2d543065287780e42da4f8b4943
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180688"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="91dc1-102">ICorDebugCode::IsIL メソッド</span><span class="sxs-lookup"><span data-stu-id="91dc1-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="91dc1-103">この"ICorDebugCode"が Microsoft intermediate language (MSIL) でコンパイルされたコードを表すかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="91dc1-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91dc1-104">構文</span><span class="sxs-lookup"><span data-stu-id="91dc1-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91dc1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91dc1-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="91dc1-106">[out]`true`場合この`ICorDebugCode`が MSIL でコンパイル。 それ以外のコードを表す`false`します。</span><span class="sxs-lookup"><span data-stu-id="91dc1-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91dc1-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="91dc1-107">Requirements</span></span>  
 <span data-ttu-id="91dc1-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91dc1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91dc1-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91dc1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91dc1-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91dc1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91dc1-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91dc1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91dc1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="91dc1-112">See also</span></span>
