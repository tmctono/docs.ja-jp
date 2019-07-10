---
title: IMetaDataAssemblyImport::FindAssembliesByName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 315d9aa6f7db51342e71ba3f8fcdc091f7707743
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777982"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="42cad-102">IMetaDataAssemblyImport::FindAssembliesByName メソッド</span><span class="sxs-lookup"><span data-stu-id="42cad-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="42cad-103">指定したアセンブリの配列を取得します`szAssemblyName`パラメーター、参照を解決するための共通言語ランタイム (CLR) で採用されている標準の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="42cad-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42cad-104">構文</span><span class="sxs-lookup"><span data-stu-id="42cad-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42cad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42cad-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="42cad-106">[in]指定されたアセンブリを検索するためのルート ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="42cad-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="42cad-107">この値が設定されている場合`null`、`FindAssembliesByName`アセンブリはグローバル アセンブリ キャッシュでのみ検索します。</span><span class="sxs-lookup"><span data-stu-id="42cad-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="42cad-108">[in]セミコロンで区切られたサブディレクトリ (たとえば、「bin、bin2」)、アセンブリを検索するためのルート ディレクトリの下の一覧。</span><span class="sxs-lookup"><span data-stu-id="42cad-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="42cad-109">これらのディレクトリは、既定のルールをプローブで指定されているだけでなく検出されます。</span><span class="sxs-lookup"><span data-stu-id="42cad-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="42cad-110">[in]検索対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="42cad-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="42cad-111">クラスのリファレンス ページでこの文字列の形式が定義されている<xref:System.Reflection.AssemblyName>します。</span><span class="sxs-lookup"><span data-stu-id="42cad-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="42cad-112">[in]型の配列[IUnknown](/cpp/atl/iunknown)配置される、`IMetadataAssemblyImport`インターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="42cad-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="42cad-113">[out]配置できるインターフェイス ポインターの最大数`ppIUnk`します。</span><span class="sxs-lookup"><span data-stu-id="42cad-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="42cad-114">[out]インターフェイス ポインターの数が返されます。</span><span class="sxs-lookup"><span data-stu-id="42cad-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="42cad-115">つまり、インターフェイス ポインターの数が実際に配置`ppIUnk`します。</span><span class="sxs-lookup"><span data-stu-id="42cad-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42cad-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="42cad-116">Return Value</span></span>  
  
|<span data-ttu-id="42cad-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42cad-117">HRESULT</span></span>|<span data-ttu-id="42cad-118">説明</span><span class="sxs-lookup"><span data-stu-id="42cad-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="42cad-119">`FindAssembliesByName` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="42cad-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="42cad-120">アセンブリがありません。</span><span class="sxs-lookup"><span data-stu-id="42cad-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42cad-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="42cad-121">Remarks</span></span>  
 <span data-ttu-id="42cad-122">特定のアセンブリ名、`FindAssembliesByName`メソッドは、アセンブリ参照を解決するための標準の規則に従って、アセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="42cad-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="42cad-123">(詳細については、次を参照してください[ランタイムがアセンブリを検索する方法](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。)。`FindAssembliesByName`により、呼び出し元アセンブリの競合回避モジュール コンテキストのアプリケーションの基本とプライベートの検索パスなどのさまざまな側面を構成します。</span><span class="sxs-lookup"><span data-stu-id="42cad-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="42cad-124">`FindAssembliesByName`メソッドが、CLR アセンブリの解決ロジックを呼び出すために、プロセスで初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42cad-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="42cad-125">そのため、呼び出す必要がある[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT を渡す) 呼び出す前に`FindAssembliesByName`への呼び出しで次の[CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="42cad-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="42cad-126">`FindAssembliesByName` 返します、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)で渡されるアセンブリの名前のアセンブリ マニフェストを含むファイルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="42cad-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="42cad-127">(たとえば、バージョンが含まれていない場合)、指定したアセンブリ名が完全に指定されていない場合は、複数のアセンブリを返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42cad-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="42cad-128">`FindAssembliesByName` コンパイル時に参照アセンブリを検索しようとするコンパイラで通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="42cad-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42cad-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="42cad-129">Requirements</span></span>  
 <span data-ttu-id="42cad-130">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42cad-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42cad-131">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="42cad-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42cad-132">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="42cad-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42cad-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42cad-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42cad-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="42cad-134">See also</span></span>

- [<span data-ttu-id="42cad-135">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="42cad-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="42cad-136">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42cad-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
