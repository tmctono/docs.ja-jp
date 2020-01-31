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
ms.openlocfilehash: a6f93ec3c7ffe415c41dcf094dbde2f0a08969f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790997"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="4d325-102">いい変数 Home:: GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="4d325-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="4d325-103">変数の基本レジスタからのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d325-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d325-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d325-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d325-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d325-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="4d325-106">入出力基本レジスタからのオフセット。</span><span class="sxs-lookup"><span data-stu-id="4d325-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d325-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4d325-107">Return Value</span></span>  
 <span data-ttu-id="4d325-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d325-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="4d325-109">Value</span><span class="sxs-lookup"><span data-stu-id="4d325-109">Value</span></span>|<span data-ttu-id="4d325-110">説明</span><span class="sxs-lookup"><span data-stu-id="4d325-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="4d325-111">変数は、レジスタ相対メモリの場所にあります。</span><span class="sxs-lookup"><span data-stu-id="4d325-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="4d325-112">変数がレジスタ相対メモリ位置にありません。</span><span class="sxs-lookup"><span data-stu-id="4d325-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d325-113">要件</span><span class="sxs-lookup"><span data-stu-id="4d325-113">Requirements</span></span>  
 <span data-ttu-id="4d325-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d325-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d325-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d325-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d325-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d325-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d325-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d325-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d325-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d325-118">See also</span></span>

- [<span data-ttu-id="4d325-119">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d325-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
