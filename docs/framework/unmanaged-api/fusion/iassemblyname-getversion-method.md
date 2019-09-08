---
title: IAssemblyName::GetVersion メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58919936bdc62d52437f429146f04c66d49294b2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796585"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="b255c-102">IAssemblyName::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="b255c-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="b255c-103">この[IAssemblyName](iassemblyname-interface.md)オブジェクトによって参照されるアセンブリのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b255c-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b255c-104">構文</span><span class="sxs-lookup"><span data-stu-id="b255c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b255c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b255c-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="b255c-106">入出力バージョンの上位32ビット。</span><span class="sxs-lookup"><span data-stu-id="b255c-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="b255c-107">入出力バージョンの下位32ビット。</span><span class="sxs-lookup"><span data-stu-id="b255c-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b255c-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="b255c-108">Requirements</span></span>  
 <span data-ttu-id="b255c-109">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b255c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b255c-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b255c-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b255c-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b255c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b255c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b255c-112">See also</span></span>

- [<span data-ttu-id="b255c-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b255c-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
