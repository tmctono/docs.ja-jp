---
title: ICorDebugProcess5::GetArrayLayout メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: ea7630efedb7b667dc58174eda0cb98d9f382cfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792384"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="66bcc-102">ICorDebugProcess5::GetArrayLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="66bcc-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="66bcc-103">配列型のレイアウトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="66bcc-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66bcc-104">構文</span><span class="sxs-lookup"><span data-stu-id="66bcc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66bcc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66bcc-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="66bcc-106">からレイアウトが必要な配列を指定する[COR_TYPEID](cor-typeid-structure.md)トークン。</span><span class="sxs-lookup"><span data-stu-id="66bcc-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="66bcc-107">入出力メモリ内の配列のレイアウトに関する情報を格納している[COR_ARRAY_LAYOUT](cor-array-layout-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="66bcc-107">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66bcc-108">コメント</span><span class="sxs-lookup"><span data-stu-id="66bcc-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66bcc-109">要件</span><span class="sxs-lookup"><span data-stu-id="66bcc-109">Requirements</span></span>  
 <span data-ttu-id="66bcc-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66bcc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66bcc-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66bcc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66bcc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66bcc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66bcc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bcc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bcc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="66bcc-114">See also</span></span>

- [<span data-ttu-id="66bcc-115">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66bcc-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="66bcc-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66bcc-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
