---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 984ec5dea757971081ce05c858788473a0f616e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775277"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="f524e-102">IMetaDataAssemblyEmit::SetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="f524e-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="f524e-103">指定された `AssemblyRef` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="f524e-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f524e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f524e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f524e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f524e-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="f524e-106">[in]メタデータ トークンを指定する、`AssemblyRef`メタデータ構造を変更します。</span><span class="sxs-lookup"><span data-stu-id="f524e-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="f524e-107">[in]参照先アセンブリの発行者の公開キー。</span><span class="sxs-lookup"><span data-stu-id="f524e-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="f524e-108">[in]バイト サイズ`pbPublicKeyOrToken`します。</span><span class="sxs-lookup"><span data-stu-id="f524e-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="f524e-109">[in]アセンブリの人間が判読できるテキストの名前。</span><span class="sxs-lookup"><span data-stu-id="f524e-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f524e-110">[in]アセンブリのバージョン、プラットフォーム、およびロケール情報を含む ASSEMBLYMETADATA インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f524e-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f524e-111">[in]アセンブリに関連付けられているデータのハッシュへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f524e-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f524e-112">[in]バイト サイズ`pbHashValue`します。</span><span class="sxs-lookup"><span data-stu-id="f524e-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="f524e-113">[in]ビットごとの組み合わせ[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)参照アセンブリの属性を指定する値。</span><span class="sxs-lookup"><span data-stu-id="f524e-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f524e-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="f524e-114">Remarks</span></span>  
 <span data-ttu-id="f524e-115">作成する、`AssemblyRef`メタデータ構造体を使用して、 [imetadataassemblyemit::defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="f524e-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f524e-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="f524e-116">Requirements</span></span>  
 <span data-ttu-id="f524e-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f524e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f524e-118">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f524e-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f524e-119">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="f524e-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f524e-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f524e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f524e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f524e-121">See also</span></span>

- [<span data-ttu-id="f524e-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f524e-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
