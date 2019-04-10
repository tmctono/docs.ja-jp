---
title: CreateAssemblyNameObject 関数
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd8609bedcea28c1cb8559d378b5e171f3ad568e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225002"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="5a91f-102">CreateAssemblyNameObject 関数</span><span class="sxs-lookup"><span data-stu-id="5a91f-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="5a91f-103">インターフェイス ポインターを取得、 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)指定した名前のアセンブリの一意の id を表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="5a91f-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a91f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a91f-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a91f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a91f-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="5a91f-106">[out]返された`IAssemblyName`します。</span><span class="sxs-lookup"><span data-stu-id="5a91f-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="5a91f-107">[in]新しいを作成する対象のアセンブリの名前`IAssemblyName`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="5a91f-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5a91f-108">[in]オブジェクトのコンス トラクターに渡すフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a91f-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="5a91f-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="5a91f-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="5a91f-110">null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a91f-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a91f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a91f-111">Requirements</span></span>  
 <span data-ttu-id="5a91f-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a91f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a91f-113">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5a91f-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5a91f-114">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5a91f-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5a91f-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5a91f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a91f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a91f-116">See also</span></span>

- [<span data-ttu-id="5a91f-117">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a91f-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="5a91f-118">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="5a91f-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
