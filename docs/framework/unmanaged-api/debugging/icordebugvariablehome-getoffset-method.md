---
title: ICorDebugVariableHome::GetOffset メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864cb893511bceabd61ce0064065b3866ce01dfe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212597"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="2537c-102">ICorDebugVariableHome::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="2537c-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="2537c-103">変数のベース レジスタからのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="2537c-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2537c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2537c-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2537c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2537c-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="2537c-106">[out]ベース レジスタからのオフセット。</span><span class="sxs-lookup"><span data-stu-id="2537c-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2537c-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2537c-107">Return Value</span></span>  
 <span data-ttu-id="2537c-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="2537c-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="2537c-109">[値]</span><span class="sxs-lookup"><span data-stu-id="2537c-109">Value</span></span>|<span data-ttu-id="2537c-110">説明</span><span class="sxs-lookup"><span data-stu-id="2537c-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2537c-111">変数は、レジスタの相対メモリの場所には。</span><span class="sxs-lookup"><span data-stu-id="2537c-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2537c-112">変数は、レジスタの相対メモリの場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="2537c-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2537c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="2537c-113">Requirements</span></span>  
 <span data-ttu-id="2537c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2537c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2537c-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2537c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2537c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2537c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2537c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2537c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2537c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2537c-118">See also</span></span>

- [<span data-ttu-id="2537c-119">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2537c-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
