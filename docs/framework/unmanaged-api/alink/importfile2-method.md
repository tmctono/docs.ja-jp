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
ms.openlocfilehash: a03fc24e5ef932d13c0d195f53c703cdd3ff45ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776936"
---
# <a name="importfile2-method"></a><span data-ttu-id="5a0d8-102">ImportFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="5a0d8-102">ImportFile2 Method</span></span>
<span data-ttu-id="5a0d8-103">アセンブリとバインドされていないモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="5a0d8-104">このメソッドは[Importfile メソッド](importfile-method.md)に似ていますが、インポートされるファイルがディスク上に存在しない場合でも機能します。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a0d8-105">構文</span><span class="sxs-lookup"><span data-stu-id="5a0d8-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="5a0d8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a0d8-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="5a0d8-107">インポートするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="5a0d8-108">アセンブリにリンクされているファイルの名前を変更するために使用できる省略可能な出力ファイル名です。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="5a0d8-109">省略可能なスコープ[IMetaDataAssemblyImport インターフェイス](../metadata/imetadataassemblyimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="5a0d8-110">TRUE の場合、ImportTypes が使用されます。それ以外の場合は、インポートを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="5a0d8-111">ファイルまたはアセンブリの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="5a0d8-112">[IMetaDataAssemblyImport インターフェイス](../metadata/imetadataassemblyimport-interface.md)インターフェイスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="5a0d8-113">ファイルがアセンブリでない場合は NULL です。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="5a0d8-114">インポートされたファイルまたはスコープの検出されたを受信します。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a0d8-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="5a0d8-115">Return Value</span></span>  
 <span data-ttu-id="5a0d8-116">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a0d8-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a0d8-117">Requirements</span></span>  
 <span data-ttu-id="5a0d8-118">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a0d8-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0d8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a0d8-119">See also</span></span>

- [<span data-ttu-id="5a0d8-120">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a0d8-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5a0d8-121">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a0d8-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5a0d8-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="5a0d8-122">ALink API</span></span>](index.md)
