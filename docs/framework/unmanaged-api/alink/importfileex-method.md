---
title: ImportFileEx メソッド
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777121"
---
# <a name="importfileex-method"></a><span data-ttu-id="4b0eb-102">ImportFileEx メソッド</span><span class="sxs-lookup"><span data-stu-id="4b0eb-102">ImportFileEx Method</span></span>
<span data-ttu-id="4b0eb-103">指定したアセンブリまたはバインドされていないモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b0eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b0eb-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b0eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b0eb-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4b0eb-106">インポート元のファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4b0eb-107">ターゲットファイルの名前 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4b0eb-108">TRUE の場合、ImportTypes が使用されます。それ以外の場合は、インポートを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="4b0eb-109">[Openscope メソッド](../metadata/imetadatadispenser-openscope-method.md)に渡されるフラグ。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4b0eb-110">インポートされるファイルの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4b0eb-111">アセンブリインポートスコープ[IMetaDataAssemblyImport インターフェイス](../metadata/imetadataassemblyimport-interface.md)インターフェイスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="4b0eb-112">ファイルがアセンブリでない場合、は NULL に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4b0eb-113">インポートされたファイルまたはスコープの数を受信します。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b0eb-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="4b0eb-114">Return Value</span></span>  
 <span data-ttu-id="4b0eb-115">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b0eb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="4b0eb-116">Requirements</span></span>  
 <span data-ttu-id="4b0eb-117">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="4b0eb-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0eb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b0eb-118">See also</span></span>

- [<span data-ttu-id="4b0eb-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b0eb-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4b0eb-120">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b0eb-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4b0eb-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="4b0eb-121">ALink API</span></span>](index.md)
