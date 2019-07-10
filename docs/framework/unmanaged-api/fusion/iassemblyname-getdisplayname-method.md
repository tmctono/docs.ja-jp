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
ms.openlocfilehash: c434595414fd5bdabeae96d959aaa6be6d84af2b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753965"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="450fd-102">IAssemblyName::GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="450fd-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="450fd-103">これによって参照されるアセンブリの人間が判読できる名前を取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="450fd-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="450fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="450fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="450fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="450fd-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="450fd-106">[out]参照先アセンブリの名前を格納している文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="450fd-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="450fd-107">[入力、出力]サイズ`szDisplayName`ワイド文字、終端の null 文字を含むです。</span><span class="sxs-lookup"><span data-stu-id="450fd-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="450fd-108">[in]ビットごとの組み合わせ[ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md)の機能に影響を与える値`szDisplayName`します。</span><span class="sxs-lookup"><span data-stu-id="450fd-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="450fd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="450fd-109">Requirements</span></span>  
 <span data-ttu-id="450fd-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="450fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="450fd-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="450fd-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="450fd-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="450fd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450fd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="450fd-113">See also</span></span>

- [<span data-ttu-id="450fd-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="450fd-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="450fd-115">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="450fd-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
