---
title: IMetaDataAssemblyEmit::DefineAssembly メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177885"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="53d82-102">IMetaDataAssemblyEmit::DefineAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="53d82-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="53d82-103">指定した`Assembly`アセンブリのメタデータを含む構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="53d82-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d82-104">構文</span><span class="sxs-lookup"><span data-stu-id="53d82-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53d82-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53d82-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="53d82-106">[in]アセンブリの発行者を識別する公開キー。</span><span class="sxs-lookup"><span data-stu-id="53d82-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="53d82-107">[in]のサイズ (バイト`pbPublicKey`単位)</span><span class="sxs-lookup"><span data-stu-id="53d82-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="53d82-108">[in]アセンブリ内のファイルの暗号化に使用するハッシュ アルゴリズムの識別子。または NULL を使用して SHA-1 アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="53d82-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="53d82-109">[in]アセンブリの人間が判読できるテキスト名。</span><span class="sxs-lookup"><span data-stu-id="53d82-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="53d82-110">この値は 1024 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="53d82-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="53d82-111">[in]アセンブリのバージョン、プラットフォーム、およびロケール情報を含む ASSEMBLYMETADATA インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="53d82-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="53d82-112">[in]アセンブリの機能を記述する[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="53d82-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="53d82-113">[アウト]メタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="53d82-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53d82-114">解説</span><span class="sxs-lookup"><span data-stu-id="53d82-114">Remarks</span></span>  
 <span data-ttu-id="53d82-115">マニフェスト内`Assembly`で定義できるメタデータ構造は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="53d82-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d82-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="53d82-116">Requirements</span></span>  
 <span data-ttu-id="53d82-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53d82-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53d82-118">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="53d82-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53d82-119">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="53d82-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53d82-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53d82-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d82-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="53d82-121">See also</span></span>

- [<span data-ttu-id="53d82-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53d82-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
