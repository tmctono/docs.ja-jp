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
ms.openlocfilehash: 20628e708261076c6e172ff30c366a0d69c2e0f2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432127"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="8e248-102">IMetaDataAssemblyEmit::DefineAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="8e248-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="8e248-103">指定したアセンブリのメタデータを含む `Assembly` 構造体を作成し、関連付けられているメタデータトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="8e248-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e248-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e248-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8e248-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e248-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="8e248-106">からアセンブリの発行元を識別する公開キー。アセンブリに厳密な名前が付けられていない場合は NULL。</span><span class="sxs-lookup"><span data-stu-id="8e248-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="8e248-107">から`pbPublicKey`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="8e248-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="8e248-108">からアセンブリ内のファイルを暗号化するために使用するハッシュアルゴリズムの識別子。または、SHA-1 アルゴリズムを指定する場合は NULL。</span><span class="sxs-lookup"><span data-stu-id="8e248-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="8e248-109">からユーザーが判読できる、アセンブリのテキスト名。</span><span class="sxs-lookup"><span data-stu-id="8e248-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="8e248-110">この値は、1024文字を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e248-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="8e248-111">からアセンブリのバージョン、プラットフォーム、およびロケール情報を格納している ASSEMBLYMETADATA インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8e248-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="8e248-112">からアセンブリの機能を記述する[Corassemblyflags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="8e248-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="8e248-113">入出力メタデータトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8e248-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e248-114">コメント</span><span class="sxs-lookup"><span data-stu-id="8e248-114">Remarks</span></span>  
 <span data-ttu-id="8e248-115">マニフェスト内で定義できる `Assembly` メタデータ構造は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="8e248-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e248-116">要件</span><span class="sxs-lookup"><span data-stu-id="8e248-116">Requirements</span></span>  
 <span data-ttu-id="8e248-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e248-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e248-118">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8e248-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e248-119">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8e248-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e248-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e248-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e248-121">参照</span><span class="sxs-lookup"><span data-stu-id="8e248-121">See also</span></span>

- [<span data-ttu-id="8e248-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e248-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
