---
title: IMetaDataImport2 インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6717c48fca14f2200f783a984594388ef3b29c15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211933"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="8c057-102">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c057-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="8c057-103">拡張、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)ジェネリック型の操作の機能を提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8c057-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c057-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-104">Methods</span></span>  
  
|<span data-ttu-id="8c057-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-105">Method</span></span>|<span data-ttu-id="8c057-106">説明</span><span class="sxs-lookup"><span data-stu-id="8c057-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c057-107">EnumGenericParamConstraints メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="8c057-108">指定したトークンによって表されるジェネリック パラメーターに関連付けられているジェネリック パラメーターの制約の配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="8c057-109">EnumGenericParams メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="8c057-110">トークンのジェネリック パラメーター トークンを指定した TypeDef または MethodDef に関連付けられた配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="8c057-111">EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="8c057-112">トークンに関連付けられた、指定した MethodDef または MemberRef MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="8c057-113">GetGenericParamConstraintProps メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="8c057-114">指定した制約トークンによって表されるジェネリック パラメーターの制約に関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="8c057-115">GetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="8c057-116">指定したトークンによって表されるジェネリック パラメーターに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="8c057-117">GetMethodSpecProps メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="8c057-118">指定した MethodSpec によって参照されるメソッドのメタデータ署名のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="8c057-119">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="8c057-120">ポータブル実行可能 (PE) でコードの性質を識別する値ファイルを取得、通常、DLL または EXE ファイルの現在のメタデータ スコープで定義されています。</span><span class="sxs-lookup"><span data-stu-id="8c057-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="8c057-121">GetVersionString メソッド</span><span class="sxs-lookup"><span data-stu-id="8c057-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="8c057-122">アセンブリのビルドに使用されたランタイムのバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c057-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c057-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c057-123">Requirements</span></span>  
 <span data-ttu-id="8c057-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c057-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c057-125">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c057-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c057-126">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8c057-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c057-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c057-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c057-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c057-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="8c057-129">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c057-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="8c057-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c057-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
