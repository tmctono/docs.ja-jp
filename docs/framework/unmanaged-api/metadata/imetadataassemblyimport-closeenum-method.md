---
title: IMetaDataAssemblyImport::CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type:
- apiref
ms.openlocfilehash: 63e81e822eb55b4090aeee6d6be3c72adbd94451
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009133"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="db13a-102">IMetaDataAssemblyImport::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="db13a-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="db13a-103">指定した列挙インスタンスへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="db13a-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db13a-104">構文</span><span class="sxs-lookup"><span data-stu-id="db13a-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db13a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db13a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="db13a-106">から閉じられる列挙体のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="db13a-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db13a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="db13a-107">Requirements</span></span>  
 <span data-ttu-id="db13a-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db13a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db13a-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="db13a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db13a-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="db13a-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db13a-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db13a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db13a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="db13a-112">See also</span></span>

- [<span data-ttu-id="db13a-113">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db13a-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
