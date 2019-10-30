---
title: 'いい変数 Home:: GetOffset メソッド'
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
ms.openlocfilehash: 3af8c925b80b9fd4ed0a46d2bd50fe37a6f3154a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125096"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="a6be3-102">いい変数 Home:: GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="a6be3-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="a6be3-103">変数の基本レジスタからのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6be3-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6be3-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6be3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6be3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6be3-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="a6be3-106">入出力基本レジスタからのオフセット。</span><span class="sxs-lookup"><span data-stu-id="a6be3-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6be3-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a6be3-107">Return Value</span></span>  
 <span data-ttu-id="a6be3-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="a6be3-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="a6be3-109">[値]</span><span class="sxs-lookup"><span data-stu-id="a6be3-109">Value</span></span>|<span data-ttu-id="a6be3-110">説明</span><span class="sxs-lookup"><span data-stu-id="a6be3-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="a6be3-111">変数は、レジスタ相対メモリの場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a6be3-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="a6be3-112">変数がレジスタ相対メモリ位置にありません。</span><span class="sxs-lookup"><span data-stu-id="a6be3-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6be3-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="a6be3-113">Requirements</span></span>  
 <span data-ttu-id="a6be3-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6be3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6be3-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6be3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6be3-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6be3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6be3-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6be3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6be3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6be3-118">See also</span></span>

- [<span data-ttu-id="a6be3-119">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6be3-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
