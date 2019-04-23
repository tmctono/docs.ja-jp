---
title: GetScope2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3c6b9e1239dc1baed9428d4fe967eb8274a9304
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206032"
---
# <a name="getscope2-method"></a><span data-ttu-id="a1946-102">GetScope2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a1946-102">GetScope2 Method</span></span>
<span data-ttu-id="a1946-103">インポート スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1946-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1946-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1946-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="a1946-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1946-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a1946-106">ターゲット アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="a1946-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a1946-107">インポート元のファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="a1946-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a1946-108">インポートする 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="a1946-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a1946-109">ポインターを受け取る[IMetaDataImport2 インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)指定のスコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a1946-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1946-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1946-110">Return Value</span></span>  
 <span data-ttu-id="a1946-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a1946-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1946-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1946-112">Requirements</span></span>  
 <span data-ttu-id="a1946-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="a1946-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1946-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1946-114">See also</span></span>

- [<span data-ttu-id="a1946-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1946-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a1946-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1946-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a1946-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="a1946-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
