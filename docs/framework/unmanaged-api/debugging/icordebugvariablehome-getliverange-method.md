---
title: 'いい変数 Home:: GetLiveRange メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: fb198782bb91a8301507fd6cadcffb0378230f0e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396579"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="42d86-102">いい変数 Home:: GetLiveRange メソッド</span><span class="sxs-lookup"><span data-stu-id="42d86-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="42d86-103">この変数がライブであるネイティブ範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="42d86-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d86-104">構文</span><span class="sxs-lookup"><span data-stu-id="42d86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42d86-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42d86-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="42d86-106">入出力変数が最初にライブになる論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="42d86-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="42d86-107">入出力変数が最後にライブになる位置の直後の論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="42d86-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42d86-108">要件</span><span class="sxs-lookup"><span data-stu-id="42d86-108">Requirements</span></span>  
 <span data-ttu-id="42d86-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42d86-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42d86-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42d86-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42d86-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42d86-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42d86-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42d86-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d86-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="42d86-113">See also</span></span>

- [<span data-ttu-id="42d86-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42d86-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
