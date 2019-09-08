---
title: IAssemblyName::GetDisplayName メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f48f2d95829d2c8111065e5f4ede4e43a16d63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796655"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="5e3ac-102">IAssemblyName::GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="5e3ac-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="5e3ac-103">この[IAssemblyName](iassemblyname-interface.md)オブジェクトによって参照されるアセンブリの、人間が判読できる名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e3ac-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e3ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e3ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e3ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e3ac-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="5e3ac-106">入出力参照されたアセンブリの名前を格納している文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="5e3ac-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="5e3ac-107">[入力、出力]Null 終端文字`szDisplayName`を含むワイド文字ののサイズ。</span><span class="sxs-lookup"><span data-stu-id="5e3ac-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="5e3ac-108">からの`szDisplayName`機能に影響を与える[ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="5e3ac-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e3ac-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e3ac-109">Requirements</span></span>  
 <span data-ttu-id="5e3ac-110">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e3ac-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e3ac-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5e3ac-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5e3ac-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e3ac-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3ac-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e3ac-113">See also</span></span>

- [<span data-ttu-id="5e3ac-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e3ac-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="5e3ac-115">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="5e3ac-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
