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
ms.openlocfilehash: 4770eb3e93104dd3862eb2163faf1dc7fe9008ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125134"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="eb656-102">いい変数 Home:: GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="eb656-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="eb656-103">このこのコード例の[ホーム](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクトを含む "コード" インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="eb656-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb656-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb656-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb656-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb656-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="eb656-106">入出力この表示[変数ホーム](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクトを含む "コード" インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eb656-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb656-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="eb656-107">Requirements</span></span>  
 <span data-ttu-id="eb656-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb656-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb656-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb656-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb656-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb656-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb656-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb656-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb656-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb656-112">See also</span></span>

- [<span data-ttu-id="eb656-113">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb656-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
