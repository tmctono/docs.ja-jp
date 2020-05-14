---
title: 'いい変数 Home:: GetCode メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 87d611a7b6e12a9238b00131326e8205778769e6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396588"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="e7ff1-102">いい変数 Home:: GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="e7ff1-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="e7ff1-103">このこのコード例の[ホーム](icordebugvariablehome-interface.md)オブジェクトを含む "コード" インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7ff1-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ff1-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7ff1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7ff1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7ff1-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="e7ff1-106">入出力この表示[変数ホーム](icordebugvariablehome-interface.md)オブジェクトを含む "コード" インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e7ff1-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7ff1-107">要件</span><span class="sxs-lookup"><span data-stu-id="e7ff1-107">Requirements</span></span>  
 <span data-ttu-id="e7ff1-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7ff1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7ff1-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7ff1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7ff1-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7ff1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7ff1-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7ff1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ff1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7ff1-112">See also</span></span>

- [<span data-ttu-id="e7ff1-113">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7ff1-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
