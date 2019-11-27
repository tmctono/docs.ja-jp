---
title: IMetaDataImport2::GetPEKind メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
ms.openlocfilehash: 0464c61e4ff01483e10fb5708d5ed4b5f5ed63d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445240"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="58b58-102">IMetaDataImport2::GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="58b58-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="58b58-103">現在のメタデータスコープで定義されている、ポータブル実行可能 (PE) ファイル (通常は DLL または EXE ファイル) 内のコードの性質を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="58b58-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b58-104">構文</span><span class="sxs-lookup"><span data-stu-id="58b58-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58b58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58b58-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="58b58-106">入出力PE ファイルを記述する[Corpekind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)列挙型の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="58b58-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="58b58-107">入出力コンピューターのアーキテクチャを識別する値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="58b58-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="58b58-108">使用可能な値については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58b58-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58b58-109">コメント</span><span class="sxs-lookup"><span data-stu-id="58b58-109">Remarks</span></span>  
 <span data-ttu-id="58b58-110">`pdwMachine` パラメーターによって参照される値には、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="58b58-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="58b58-111">値</span><span class="sxs-lookup"><span data-stu-id="58b58-111">Value</span></span>|<span data-ttu-id="58b58-112">コンピューターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="58b58-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="58b58-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="58b58-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="58b58-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="58b58-114">0x014C</span></span>|<span data-ttu-id="58b58-115">x86</span><span class="sxs-lookup"><span data-stu-id="58b58-115">x86</span></span>|  
|<span data-ttu-id="58b58-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="58b58-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="58b58-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="58b58-117">0x0200</span></span>|<span data-ttu-id="58b58-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="58b58-118">Intel IPF</span></span>|  
|<span data-ttu-id="58b58-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="58b58-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="58b58-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="58b58-120">0x8664</span></span>|<span data-ttu-id="58b58-121">x64</span><span class="sxs-lookup"><span data-stu-id="58b58-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58b58-122">要件</span><span class="sxs-lookup"><span data-stu-id="58b58-122">Requirements</span></span>  
 <span data-ttu-id="58b58-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58b58-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b58-124">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="58b58-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58b58-125">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="58b58-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58b58-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b58-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b58-127">参照</span><span class="sxs-lookup"><span data-stu-id="58b58-127">See also</span></span>

- [<span data-ttu-id="58b58-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58b58-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="58b58-129">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58b58-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="58b58-130">CorPEKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="58b58-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
