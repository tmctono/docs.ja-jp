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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176046"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="d7dcb-102">IMetaDataAssemblyEmit::SetAssemblyRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="d7dcb-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="d7dcb-103">指定された `AssemblyRef` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7dcb-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7dcb-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d7dcb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7dcb-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="d7dcb-106">[in]変更するメタデータ構造を`AssemblyRef`指定するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="d7dcb-107">[in]参照アセンブリの発行者の公開キー。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="d7dcb-108">[in]のサイズ (バイト`pbPublicKeyOrToken`単位)</span><span class="sxs-lookup"><span data-stu-id="d7dcb-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="d7dcb-109">[in]アセンブリの人間が判読できるテキスト名。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d7dcb-110">[in]アセンブリのバージョン、プラットフォーム、およびロケール情報を含む ASSEMBLYMETADATA インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d7dcb-111">[in]アセンブリに関連付けられているハッシュ データへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d7dcb-112">[in]のサイズ (バイト`pbHashValue`単位)</span><span class="sxs-lookup"><span data-stu-id="d7dcb-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="d7dcb-113">[in]参照先アセンブリの属性を指定する[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7dcb-114">解説</span><span class="sxs-lookup"><span data-stu-id="d7dcb-114">Remarks</span></span>  
 <span data-ttu-id="d7dcb-115">メタデータ構造を`AssemblyRef`作成するには[、IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7dcb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7dcb-116">Requirements</span></span>  
 <span data-ttu-id="d7dcb-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7dcb-118">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="d7dcb-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7dcb-119">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7dcb-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7dcb-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7dcb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dcb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7dcb-121">See also</span></span>

- [<span data-ttu-id="d7dcb-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7dcb-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
