---
title: IMetaDataEmit::SetModuleProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 651659a48ba9950cdd837889c4491c66fe40b507
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042974"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="26124-102">IMetaDataEmit::SetModuleProps メソッド</span><span class="sxs-lookup"><span data-stu-id="26124-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="26124-103">前回の呼び出しで定義されているモジュールへの参照を更新[imetadataemit::definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="26124-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26124-104">構文</span><span class="sxs-lookup"><span data-stu-id="26124-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26124-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26124-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="26124-106">[in]Unicode でモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="26124-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="26124-107">これは、ファイル名のみの完全なパス名ではありません。</span><span class="sxs-lookup"><span data-stu-id="26124-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26124-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="26124-108">Requirements</span></span>  
 <span data-ttu-id="26124-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26124-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26124-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="26124-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26124-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="26124-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26124-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26124-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26124-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="26124-113">See also</span></span>

- [<span data-ttu-id="26124-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26124-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="26124-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26124-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
