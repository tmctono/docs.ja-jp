---
title: ImportFile2 メソッド
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88006703ba4a491ae458868a1431be618d37252a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471200"
---
# <a name="importfile2-method"></a><span data-ttu-id="0695e-102">ImportFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="0695e-102">ImportFile2 Method</span></span>
<span data-ttu-id="0695e-103">アセンブリとバインドされていないモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="0695e-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="0695e-104">このメソッドはのように、 [ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)がインポートされるファイルがディスクに存在しない場合でも機能します。</span><span class="sxs-lookup"><span data-stu-id="0695e-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0695e-105">構文</span><span class="sxs-lookup"><span data-stu-id="0695e-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0695e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0695e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="0695e-107">インポートするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="0695e-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="0695e-108">省略可能な出力ファイル名、アセンブリにリンクされていると、ファイルの名前を変更するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0695e-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="0695e-109">省略可能なスコープ[IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="0695e-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="0695e-110">TRUE の場合は、ImportTypes が使用されますが、それ以外の場合にインポートし、手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0695e-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="0695e-111">ファイルまたはアセンブリの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0695e-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="0695e-112">受信、 [IMetaDataAssemblyImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="0695e-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="0695e-113">ファイルはアセンブリでない場合は NULL です。</span><span class="sxs-lookup"><span data-stu-id="0695e-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="0695e-114">ファイルやインポート スコープには、検出されたを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0695e-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0695e-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="0695e-115">Return Value</span></span>  
 <span data-ttu-id="0695e-116">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="0695e-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0695e-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="0695e-117">Requirements</span></span>  
 <span data-ttu-id="0695e-118">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="0695e-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0695e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0695e-119">See also</span></span>
- [<span data-ttu-id="0695e-120">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0695e-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0695e-121">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0695e-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0695e-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="0695e-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
