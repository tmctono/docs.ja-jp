---
title: IAssemblyName::GetName メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e471ee99af57ef980850c0a5d3e4f5f2973967ac
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796604"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="b1ae7-102">IAssemblyName::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="b1ae7-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="b1ae7-103">この[IAssemblyName](iassemblyname-interface.md)オブジェクトによって参照されるアセンブリの単純な、暗号化されていない名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="b1ae7-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ae7-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1ae7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1ae7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1ae7-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="b1ae7-106">[入力、出力]Null 終端文字`pwzName`を含むワイド文字ののサイズ。</span><span class="sxs-lookup"><span data-stu-id="b1ae7-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="b1ae7-107">入出力参照されたアセンブリの名前を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="b1ae7-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1ae7-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1ae7-108">Requirements</span></span>  
 <span data-ttu-id="b1ae7-109">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ae7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1ae7-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b1ae7-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b1ae7-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1ae7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ae7-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1ae7-112">See also</span></span>

- [<span data-ttu-id="b1ae7-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1ae7-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
