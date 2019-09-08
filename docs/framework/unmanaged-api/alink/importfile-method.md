---
title: ImportFile メソッド
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7fee7a91de99e2db69609cbc7c73e22d85d045f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777062"
---
# <a name="importfile-method"></a><span data-ttu-id="9b6d5-102">ImportFile メソッド</span><span class="sxs-lookup"><span data-stu-id="9b6d5-102">ImportFile Method</span></span>
<span data-ttu-id="9b6d5-103">アセンブリとバインドされていないモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6d5-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b6d5-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b6d5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b6d5-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="9b6d5-106">インポートするファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="9b6d5-107">アセンブリにリンクされているファイルの名前を変更するために使用できる省略可能な出力ファイル名です。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="9b6d5-108">TRUE の場合、ImportTypes が使用されます。それ以外の場合は、インポートを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="9b6d5-109">一意のファイル ID が格納されるトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="9b6d5-110">ファイルには、アセンブリまたはファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="9b6d5-111">[IMetaDataAssemblyImport インターフェイス](../metadata/imetadataassemblyimport-interface.md)へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="9b6d5-112">ファイルがアセンブリでない場合は NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="9b6d5-113">インポートされたファイルまたはスコープの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b6d5-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="9b6d5-114">Return Value</span></span>  
 <span data-ttu-id="9b6d5-115">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b6d5-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b6d5-116">Requirements</span></span>  
 <span data-ttu-id="9b6d5-117">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b6d5-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6d5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b6d5-118">See also</span></span>

- [<span data-ttu-id="9b6d5-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b6d5-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9b6d5-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b6d5-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9b6d5-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="9b6d5-121">ALink API</span></span>](index.md)
