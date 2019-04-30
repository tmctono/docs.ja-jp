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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc0a4f52747cbc88a26f4b9aaff6642b6c1d62f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044710"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="a4ee0-102">IMetaDataAssemblyImport::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="a4ee0-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="a4ee0-103">指定した列挙体のインスタンスへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="a4ee0-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ee0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a4ee0-104">Syntax</span></span>  
  
```  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4ee0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4ee0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a4ee0-106">[in]終了する列挙体のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="a4ee0-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4ee0-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a4ee0-107">Requirements</span></span>  
 <span data-ttu-id="a4ee0-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ee0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ee0-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a4ee0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4ee0-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a4ee0-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4ee0-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ee0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ee0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4ee0-112">See also</span></span>

- [<span data-ttu-id="a4ee0-113">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4ee0-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
