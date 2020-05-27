---
title: IMetaDataAssemblyImport::GetAssemblyFromScope メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: adcaac02526c7d72ffb75ba6c7552632173032cf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009042"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="0da92-102">IMetaDataAssemblyImport::GetAssemblyFromScope メソッド</span><span class="sxs-lookup"><span data-stu-id="0da92-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="0da92-103">現在のスコープ内のアセンブリへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0da92-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da92-104">構文</span><span class="sxs-lookup"><span data-stu-id="0da92-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da92-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0da92-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="0da92-106">入出力アセンブリを識別する、取得されたトークンへのポインター `mdAssembly` 。</span><span class="sxs-lookup"><span data-stu-id="0da92-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da92-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="0da92-107">Requirements</span></span>  
 <span data-ttu-id="0da92-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da92-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da92-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="0da92-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0da92-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0da92-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0da92-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da92-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da92-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0da92-112">See also</span></span>

- [<span data-ttu-id="0da92-113">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0da92-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
