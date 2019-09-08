---
title: ImportTypes メソッド
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f19dd114925ed1fd12bcc0056411c3e3d4181215
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777089"
---
# <a name="importtypes-method"></a><span data-ttu-id="23f7b-102">ImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="23f7b-102">ImportTypes Method</span></span>
<span data-ttu-id="23f7b-103">[Importfile メソッド](importfile-method.md)を使用してインポートされた各スコープからの型のインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="23f7b-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f7b-104">構文</span><span class="sxs-lookup"><span data-stu-id="23f7b-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="23f7b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23f7b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="23f7b-106">インポート先のアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="23f7b-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="23f7b-107">インポート元のファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="23f7b-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="23f7b-108">インポートする0から始まるスコープ。</span><span class="sxs-lookup"><span data-stu-id="23f7b-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="23f7b-109">このスコープ内の型の列挙子ハンドルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="23f7b-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="23f7b-110">必要に応じて、 [IMetaDataImport インターフェイス](../metadata/imetadataimport-interface.md)インターフェイスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="23f7b-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="23f7b-111">必要に応じて、指定されたスコープ内の型の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="23f7b-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23f7b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="23f7b-112">Return Value</span></span>  
 <span data-ttu-id="23f7b-113">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="23f7b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f7b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="23f7b-114">Requirements</span></span>  
 <span data-ttu-id="23f7b-115">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="23f7b-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f7b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23f7b-116">See also</span></span>

- [<span data-ttu-id="23f7b-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23f7b-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="23f7b-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23f7b-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="23f7b-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="23f7b-119">ALink API</span></span>](index.md)
