---
title: 'いい変数 Home:: GetRegister メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790988"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="a1a21-102">いい変数 Home:: GetRegister メソッド</span><span class="sxs-lookup"><span data-stu-id="a1a21-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="a1a21-103">`VLT_REGISTER`の場所の種類を持つ変数と、場所の種類が `VLT_REGISTER_RELATIVE`の変数の基本レジスタを含むレジスタを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1a21-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1a21-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1a21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1a21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1a21-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="a1a21-106">入出力`VLT_REGISTER`の場所の種類を持つ変数のレジスタと、`VLT_REGISTER_RELATIVE`の場所の種類を持つ変数の基本レジスタを示す CorDebugRegister 列挙値。</span><span class="sxs-lookup"><span data-stu-id="a1a21-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1a21-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1a21-107">Return Value</span></span>  
 <span data-ttu-id="a1a21-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="a1a21-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="a1a21-109">Value</span><span class="sxs-lookup"><span data-stu-id="a1a21-109">Value</span></span>|<span data-ttu-id="a1a21-110">説明</span><span class="sxs-lookup"><span data-stu-id="a1a21-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="a1a21-111">変数は、`pRegister` 引数によって示されるレジスタにあります。</span><span class="sxs-lookup"><span data-stu-id="a1a21-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="a1a21-112">変数がレジスタまたはレジスタの相対位置にありません。</span><span class="sxs-lookup"><span data-stu-id="a1a21-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1a21-113">要件</span><span class="sxs-lookup"><span data-stu-id="a1a21-113">Requirements</span></span>  
 <span data-ttu-id="a1a21-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a21-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1a21-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1a21-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1a21-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1a21-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1a21-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1a21-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a21-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1a21-118">See also</span></span>

- [<span data-ttu-id="a1a21-119">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a1a21-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="a1a21-120">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1a21-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
