---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186940"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="08e7c-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="08e7c-102">OLE DB Schema Collections</span></span>

<span data-ttu-id="08e7c-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="08e7c-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="08e7c-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="08e7c-104">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="08e7c-105">Microsoft SQL Server OLE DB Driver では、共通のスキーマ コレクションに加えて、次の特定のスキーマ コレクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="08e7c-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="08e7c-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="08e7c-106">Tables</span></span>  
  
- <span data-ttu-id="08e7c-107">列</span><span class="sxs-lookup"><span data-stu-id="08e7c-107">Columns</span></span>  
  
- <span data-ttu-id="08e7c-108">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="08e7c-108">Procedures</span></span>  
  
- <span data-ttu-id="08e7c-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="08e7c-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="08e7c-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="08e7c-110">Catalog</span></span>  
  
- <span data-ttu-id="08e7c-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="08e7c-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="08e7c-112">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="08e7c-112">Tables</span></span>  
  
|<span data-ttu-id="08e7c-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-113">ColumnName</span></span>|<span data-ttu-id="08e7c-114">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-115">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-116">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-116">String</span></span>|  
|<span data-ttu-id="08e7c-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-118">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-118">String</span></span>|  
|<span data-ttu-id="08e7c-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-119">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-120">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-120">String</span></span>|  
|<span data-ttu-id="08e7c-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-121">TABLE_TYPE</span></span>|<span data-ttu-id="08e7c-122">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-122">String</span></span>|  
|<span data-ttu-id="08e7c-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-123">TABLE_GUID</span></span>|<span data-ttu-id="08e7c-124">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-124">Guid</span></span>|  
|<span data-ttu-id="08e7c-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-125">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-126">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-126">String</span></span>|  
|<span data-ttu-id="08e7c-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-127">TABLE_PROPID</span></span>|<span data-ttu-id="08e7c-128">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-128">Int64</span></span>|  
|<span data-ttu-id="08e7c-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-129">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-130">DateTime</span></span>|  
|<span data-ttu-id="08e7c-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-131">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="08e7c-133">列</span><span class="sxs-lookup"><span data-stu-id="08e7c-133">Columns</span></span>  
  
|<span data-ttu-id="08e7c-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-134">ColumnName</span></span>|<span data-ttu-id="08e7c-135">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-136">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-137">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-137">String</span></span>|  
|<span data-ttu-id="08e7c-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-139">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-139">String</span></span>|  
|<span data-ttu-id="08e7c-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-140">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-141">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-141">String</span></span>|  
|<span data-ttu-id="08e7c-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-142">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-143">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-143">String</span></span>|  
|<span data-ttu-id="08e7c-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-144">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-145">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-145">Guid</span></span>|  
|<span data-ttu-id="08e7c-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-146">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-147">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-147">Int64</span></span>|  
|<span data-ttu-id="08e7c-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-149">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-149">Int64</span></span>|  
|<span data-ttu-id="08e7c-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="08e7c-151">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-151">Boolean</span></span>|  
|<span data-ttu-id="08e7c-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="08e7c-153">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-153">String</span></span>|  
|<span data-ttu-id="08e7c-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="08e7c-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="08e7c-155">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-155">Int64</span></span>|  
|<span data-ttu-id="08e7c-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-156">IS_NULLABLE</span></span>|<span data-ttu-id="08e7c-157">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-157">Boolean</span></span>|  
|<span data-ttu-id="08e7c-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-158">DATA_TYPE</span></span>|<span data-ttu-id="08e7c-159">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-159">Int32</span></span>|  
|<span data-ttu-id="08e7c-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-160">TYPE_GUID</span></span>|<span data-ttu-id="08e7c-161">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-161">Guid</span></span>|  
|<span data-ttu-id="08e7c-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="08e7c-163">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-163">Int64</span></span>|  
|<span data-ttu-id="08e7c-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="08e7c-165">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-165">Int64</span></span>|  
|<span data-ttu-id="08e7c-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="08e7c-167">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-167">Int32</span></span>|  
|<span data-ttu-id="08e7c-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="08e7c-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="08e7c-169">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-169">Int16</span></span>|  
|<span data-ttu-id="08e7c-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="08e7c-171">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-171">Int64</span></span>|  
|<span data-ttu-id="08e7c-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="08e7c-173">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-173">String</span></span>|  
|<span data-ttu-id="08e7c-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="08e7c-175">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-175">String</span></span>|  
|<span data-ttu-id="08e7c-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="08e7c-177">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-177">String</span></span>|  
|<span data-ttu-id="08e7c-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="08e7c-179">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-179">String</span></span>|  
|<span data-ttu-id="08e7c-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="08e7c-181">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-181">String</span></span>|  
|<span data-ttu-id="08e7c-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-182">COLLATION_NAME</span></span>|<span data-ttu-id="08e7c-183">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-183">String</span></span>|  
|<span data-ttu-id="08e7c-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="08e7c-185">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-185">String</span></span>|  
|<span data-ttu-id="08e7c-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="08e7c-187">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-187">String</span></span>|  
|<span data-ttu-id="08e7c-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-188">DOMAIN_NAME</span></span>|<span data-ttu-id="08e7c-189">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-189">String</span></span>|  
|<span data-ttu-id="08e7c-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-190">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-191">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-191">String</span></span>|  
|<span data-ttu-id="08e7c-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="08e7c-192">COLUMN_LCID</span></span>|<span data-ttu-id="08e7c-193">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-193">Int32</span></span>|  
|<span data-ttu-id="08e7c-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="08e7c-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="08e7c-195">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-195">Int32</span></span>|  
|<span data-ttu-id="08e7c-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="08e7c-196">COLUMN_SORTID</span></span>|<span data-ttu-id="08e7c-197">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-197">Int32</span></span>|  
|<span data-ttu-id="08e7c-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="08e7c-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="08e7c-199">Byte[]</span></span>|  
|<span data-ttu-id="08e7c-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="08e7c-200">IS_COMPUTED</span></span>|<span data-ttu-id="08e7c-201">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="08e7c-202">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="08e7c-202">Procedures</span></span>  
  
|<span data-ttu-id="08e7c-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-203">ColumnName</span></span>|<span data-ttu-id="08e7c-204">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="08e7c-206">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-206">String</span></span>|  
|<span data-ttu-id="08e7c-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="08e7c-208">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-208">String</span></span>|  
|<span data-ttu-id="08e7c-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="08e7c-210">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-210">String</span></span>|  
|<span data-ttu-id="08e7c-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="08e7c-212">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-212">Int16</span></span>|  
|<span data-ttu-id="08e7c-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="08e7c-214">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-214">String</span></span>|  
|<span data-ttu-id="08e7c-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-215">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-216">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-216">String</span></span>|  
|<span data-ttu-id="08e7c-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-217">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-218">DateTime</span></span>|  
|<span data-ttu-id="08e7c-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-219">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="08e7c-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="08e7c-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="08e7c-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-222">ColumnName</span></span>|<span data-ttu-id="08e7c-223">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="08e7c-225">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-225">String</span></span>|  
|<span data-ttu-id="08e7c-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="08e7c-227">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-227">String</span></span>|  
|<span data-ttu-id="08e7c-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="08e7c-229">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-229">String</span></span>|  
|<span data-ttu-id="08e7c-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-230">PARAMETER_NAME</span></span>|<span data-ttu-id="08e7c-231">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-231">String</span></span>|  
|<span data-ttu-id="08e7c-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-233">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-233">Int32</span></span>|  
|<span data-ttu-id="08e7c-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="08e7c-235">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-235">Int32</span></span>|  
|<span data-ttu-id="08e7c-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="08e7c-237">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-237">Boolean</span></span>|  
|<span data-ttu-id="08e7c-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="08e7c-239">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-239">String</span></span>|  
|<span data-ttu-id="08e7c-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-240">IS_NULLABLE</span></span>|<span data-ttu-id="08e7c-241">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-241">Boolean</span></span>|  
|<span data-ttu-id="08e7c-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-242">DATA_TYPE</span></span>|<span data-ttu-id="08e7c-243">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-243">Int32</span></span>|  
|<span data-ttu-id="08e7c-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="08e7c-245">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-245">Int64</span></span>|  
|<span data-ttu-id="08e7c-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="08e7c-247">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-247">Int64</span></span>|  
|<span data-ttu-id="08e7c-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="08e7c-249">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-249">Int32</span></span>|  
|<span data-ttu-id="08e7c-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="08e7c-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="08e7c-251">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-251">Int16</span></span>|  
|<span data-ttu-id="08e7c-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-252">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-253">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-253">String</span></span>|  
|<span data-ttu-id="08e7c-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-254">TYPE_NAME</span></span>|<span data-ttu-id="08e7c-255">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-255">String</span></span>|  
|<span data-ttu-id="08e7c-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="08e7c-257">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="08e7c-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="08e7c-258">Catalog</span></span>  
  
|<span data-ttu-id="08e7c-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-259">ColumnName</span></span>|<span data-ttu-id="08e7c-260">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-261">CATALOG_NAME</span></span>|<span data-ttu-id="08e7c-262">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-262">String</span></span>|  
|<span data-ttu-id="08e7c-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-263">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-264">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="08e7c-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="08e7c-265">Indexes</span></span>  
  
|<span data-ttu-id="08e7c-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-266">ColumnName</span></span>|<span data-ttu-id="08e7c-267">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-268">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-269">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-269">String</span></span>|  
|<span data-ttu-id="08e7c-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-271">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-271">String</span></span>|  
|<span data-ttu-id="08e7c-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-272">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-273">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-273">String</span></span>|  
|<span data-ttu-id="08e7c-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-274">INDEX_CATALOG</span></span>|<span data-ttu-id="08e7c-275">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-275">String</span></span>|  
|<span data-ttu-id="08e7c-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="08e7c-277">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-277">String</span></span>|  
|<span data-ttu-id="08e7c-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-278">INDEX_NAME</span></span>|<span data-ttu-id="08e7c-279">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-279">String</span></span>|  
|<span data-ttu-id="08e7c-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="08e7c-280">PRIMARY_KEY</span></span>|<span data-ttu-id="08e7c-281">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-281">Boolean</span></span>|  
|<span data-ttu-id="08e7c-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="08e7c-282">UNIQUE</span></span>|<span data-ttu-id="08e7c-283">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-283">Boolean</span></span>|  
|<span data-ttu-id="08e7c-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="08e7c-284">CLUSTERED</span></span>|<span data-ttu-id="08e7c-285">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-285">Boolean</span></span>|  
|<span data-ttu-id="08e7c-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-286">TYPE</span></span>|<span data-ttu-id="08e7c-287">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-287">Int32</span></span>|  
|<span data-ttu-id="08e7c-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="08e7c-288">FILL_FACTOR</span></span>|<span data-ttu-id="08e7c-289">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-289">Int32</span></span>|  
|<span data-ttu-id="08e7c-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="08e7c-290">INITIAL_SIZE</span></span>|<span data-ttu-id="08e7c-291">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-291">Int32</span></span>|  
|<span data-ttu-id="08e7c-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="08e7c-292">NULLS</span></span>|<span data-ttu-id="08e7c-293">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-293">Int32</span></span>|  
|<span data-ttu-id="08e7c-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="08e7c-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="08e7c-295">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-295">Boolean</span></span>|  
|<span data-ttu-id="08e7c-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="08e7c-296">AUTO_UPDATE</span></span>|<span data-ttu-id="08e7c-297">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-297">Boolean</span></span>|  
|<span data-ttu-id="08e7c-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-298">NULL_COLLATION</span></span>|<span data-ttu-id="08e7c-299">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-299">Int32</span></span>|  
|<span data-ttu-id="08e7c-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-301">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-301">Int64</span></span>|  
|<span data-ttu-id="08e7c-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-302">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-303">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-303">String</span></span>|  
|<span data-ttu-id="08e7c-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-304">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-305">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-305">Guid</span></span>|  
|<span data-ttu-id="08e7c-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-306">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-307">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-307">Int64</span></span>|  
|<span data-ttu-id="08e7c-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-308">COLLATION</span></span>|<span data-ttu-id="08e7c-309">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-309">Int16</span></span>|  
|<span data-ttu-id="08e7c-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="08e7c-310">CARDINALITY</span></span>|<span data-ttu-id="08e7c-311">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="08e7c-311">Decimal</span></span>|  
|<span data-ttu-id="08e7c-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="08e7c-312">PAGES</span></span>|<span data-ttu-id="08e7c-313">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-313">Int32</span></span>|  
|<span data-ttu-id="08e7c-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-314">FILTER_CONDITION</span></span>|<span data-ttu-id="08e7c-315">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-315">String</span></span>|  
|<span data-ttu-id="08e7c-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-316">INTEGRATED</span></span>|<span data-ttu-id="08e7c-317">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="08e7c-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="08e7c-318">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="08e7c-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="08e7c-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="08e7c-320">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="08e7c-320">Tables</span></span>  
  
- <span data-ttu-id="08e7c-321">列</span><span class="sxs-lookup"><span data-stu-id="08e7c-321">Columns</span></span>  
  
- <span data-ttu-id="08e7c-322">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="08e7c-322">Procedures</span></span>  
  
- <span data-ttu-id="08e7c-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="08e7c-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="08e7c-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="08e7c-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="08e7c-325">Views</span><span class="sxs-lookup"><span data-stu-id="08e7c-325">Views</span></span>  
  
- <span data-ttu-id="08e7c-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="08e7c-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="08e7c-327">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="08e7c-327">Tables</span></span>  
  
|<span data-ttu-id="08e7c-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-328">ColumnName</span></span>|<span data-ttu-id="08e7c-329">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-330">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-331">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-331">String</span></span>|  
|<span data-ttu-id="08e7c-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-333">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-333">String</span></span>|  
|<span data-ttu-id="08e7c-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-334">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-335">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-335">String</span></span>|  
|<span data-ttu-id="08e7c-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-336">TABLE_TYPE</span></span>|<span data-ttu-id="08e7c-337">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-337">String</span></span>|  
|<span data-ttu-id="08e7c-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-338">TABLE_GUID</span></span>|<span data-ttu-id="08e7c-339">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-339">Guid</span></span>|  
|<span data-ttu-id="08e7c-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-340">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-341">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-341">String</span></span>|  
|<span data-ttu-id="08e7c-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-342">TABLE_PROPID</span></span>|<span data-ttu-id="08e7c-343">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-343">Int64</span></span>|  
|<span data-ttu-id="08e7c-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-344">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-345">DateTime</span></span>|  
|<span data-ttu-id="08e7c-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-346">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="08e7c-348">列</span><span class="sxs-lookup"><span data-stu-id="08e7c-348">Columns</span></span>  
  
|<span data-ttu-id="08e7c-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-349">ColumnName</span></span>|<span data-ttu-id="08e7c-350">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-351">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-352">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-352">String</span></span>|  
|<span data-ttu-id="08e7c-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-354">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-354">String</span></span>|  
|<span data-ttu-id="08e7c-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-355">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-356">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-356">String</span></span>|  
|<span data-ttu-id="08e7c-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-357">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-358">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-358">String</span></span>|  
|<span data-ttu-id="08e7c-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-359">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-360">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-360">Guid</span></span>|  
|<span data-ttu-id="08e7c-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-361">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-362">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-362">Int64</span></span>|  
|<span data-ttu-id="08e7c-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-364">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-364">Int64</span></span>|  
|<span data-ttu-id="08e7c-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="08e7c-366">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-366">Boolean</span></span>|  
|<span data-ttu-id="08e7c-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="08e7c-368">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-368">String</span></span>|  
|<span data-ttu-id="08e7c-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="08e7c-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="08e7c-370">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-370">Int64</span></span>|  
|<span data-ttu-id="08e7c-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-371">IS_NULLABLE</span></span>|<span data-ttu-id="08e7c-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-372">Boolean</span></span>|  
|<span data-ttu-id="08e7c-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-373">DATA_TYPE</span></span>|<span data-ttu-id="08e7c-374">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-374">Int32</span></span>|  
|<span data-ttu-id="08e7c-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-375">TYPE_GUID</span></span>|<span data-ttu-id="08e7c-376">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-376">Guid</span></span>|  
|<span data-ttu-id="08e7c-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="08e7c-378">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-378">Int64</span></span>|  
|<span data-ttu-id="08e7c-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="08e7c-380">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-380">Int64</span></span>|  
|<span data-ttu-id="08e7c-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="08e7c-382">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-382">Int32</span></span>|  
|<span data-ttu-id="08e7c-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="08e7c-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="08e7c-384">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-384">Int16</span></span>|  
|<span data-ttu-id="08e7c-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="08e7c-386">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-386">Int64</span></span>|  
|<span data-ttu-id="08e7c-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="08e7c-388">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-388">String</span></span>|  
|<span data-ttu-id="08e7c-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="08e7c-390">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-390">String</span></span>|  
|<span data-ttu-id="08e7c-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="08e7c-392">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-392">String</span></span>|  
|<span data-ttu-id="08e7c-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="08e7c-394">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-394">String</span></span>|  
|<span data-ttu-id="08e7c-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="08e7c-396">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-396">String</span></span>|  
|<span data-ttu-id="08e7c-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-397">COLLATION_NAME</span></span>|<span data-ttu-id="08e7c-398">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-398">String</span></span>|  
|<span data-ttu-id="08e7c-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="08e7c-400">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-400">String</span></span>|  
|<span data-ttu-id="08e7c-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="08e7c-402">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-402">String</span></span>|  
|<span data-ttu-id="08e7c-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-403">DOMAIN_NAME</span></span>|<span data-ttu-id="08e7c-404">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-404">String</span></span>|  
|<span data-ttu-id="08e7c-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-405">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-406">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="08e7c-407">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="08e7c-407">Procedures</span></span>  
  
|<span data-ttu-id="08e7c-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-408">ColumnName</span></span>|<span data-ttu-id="08e7c-409">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="08e7c-411">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-411">String</span></span>|  
|<span data-ttu-id="08e7c-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="08e7c-413">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-413">String</span></span>|  
|<span data-ttu-id="08e7c-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="08e7c-415">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-415">String</span></span>|  
|<span data-ttu-id="08e7c-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="08e7c-417">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-417">Int16</span></span>|  
|<span data-ttu-id="08e7c-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="08e7c-419">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-419">String</span></span>|  
|<span data-ttu-id="08e7c-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-420">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-421">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-421">String</span></span>|  
|<span data-ttu-id="08e7c-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-422">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-423">DateTime</span></span>|  
|<span data-ttu-id="08e7c-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-424">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="08e7c-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="08e7c-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="08e7c-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-427">ColumnName</span></span>|<span data-ttu-id="08e7c-428">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="08e7c-430">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-430">String</span></span>|  
|<span data-ttu-id="08e7c-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="08e7c-432">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-432">String</span></span>|  
|<span data-ttu-id="08e7c-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="08e7c-434">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-434">String</span></span>|  
|<span data-ttu-id="08e7c-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-435">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-436">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-436">String</span></span>|  
|<span data-ttu-id="08e7c-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-437">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-438">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-438">Guid</span></span>|  
|<span data-ttu-id="08e7c-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-439">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-440">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-440">Int64</span></span>|  
|<span data-ttu-id="08e7c-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="08e7c-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="08e7c-442">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-442">Int64</span></span>|  
|<span data-ttu-id="08e7c-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-444">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-444">Int64</span></span>|  
|<span data-ttu-id="08e7c-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-445">IS_NULLABLE</span></span>|<span data-ttu-id="08e7c-446">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-446">Boolean</span></span>|  
|<span data-ttu-id="08e7c-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-447">DATA_TYPE</span></span>|<span data-ttu-id="08e7c-448">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-448">Int32</span></span>|  
|<span data-ttu-id="08e7c-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-449">TYPE_GUID</span></span>|<span data-ttu-id="08e7c-450">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-450">Guid</span></span>|  
|<span data-ttu-id="08e7c-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="08e7c-452">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-452">Int64</span></span>|  
|<span data-ttu-id="08e7c-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="08e7c-454">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-454">Int64</span></span>|  
|<span data-ttu-id="08e7c-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="08e7c-456">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-456">Int32</span></span>|  
|<span data-ttu-id="08e7c-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="08e7c-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="08e7c-458">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-458">Int16</span></span>|  
|<span data-ttu-id="08e7c-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-459">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-460">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-460">String</span></span>|  
|<span data-ttu-id="08e7c-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="08e7c-461">OVERLOAD</span></span>|<span data-ttu-id="08e7c-462">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="08e7c-463">Views</span><span class="sxs-lookup"><span data-stu-id="08e7c-463">Views</span></span>  
  
|<span data-ttu-id="08e7c-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-464">ColumnName</span></span>|<span data-ttu-id="08e7c-465">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-466">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-467">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-467">String</span></span>|  
|<span data-ttu-id="08e7c-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-469">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-469">String</span></span>|  
|<span data-ttu-id="08e7c-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-470">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-471">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-471">String</span></span>|  
|<span data-ttu-id="08e7c-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="08e7c-473">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-473">String</span></span>|  
|<span data-ttu-id="08e7c-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-474">CHECK_OPTION</span></span>|<span data-ttu-id="08e7c-475">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-475">Boolean</span></span>|  
|<span data-ttu-id="08e7c-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-476">IS_UPDATABLE</span></span>|<span data-ttu-id="08e7c-477">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-477">Boolean</span></span>|  
|<span data-ttu-id="08e7c-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-478">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-479">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-479">String</span></span>|  
|<span data-ttu-id="08e7c-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-480">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-481">DateTime</span></span>|  
|<span data-ttu-id="08e7c-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-482">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="08e7c-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="08e7c-484">Indexes</span></span>  
  
|<span data-ttu-id="08e7c-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-485">ColumnName</span></span>|<span data-ttu-id="08e7c-486">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-487">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-488">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-488">String</span></span>|  
|<span data-ttu-id="08e7c-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-490">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-490">String</span></span>|  
|<span data-ttu-id="08e7c-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-491">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-492">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-492">String</span></span>|  
|<span data-ttu-id="08e7c-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-493">INDEX_CATALOG</span></span>|<span data-ttu-id="08e7c-494">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-494">String</span></span>|  
|<span data-ttu-id="08e7c-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="08e7c-496">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-496">String</span></span>|  
|<span data-ttu-id="08e7c-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-497">INDEX_NAME</span></span>|<span data-ttu-id="08e7c-498">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-498">String</span></span>|  
|<span data-ttu-id="08e7c-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="08e7c-499">PRIMARY_KEY</span></span>|<span data-ttu-id="08e7c-500">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-500">Boolean</span></span>|  
|<span data-ttu-id="08e7c-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="08e7c-501">UNIQUE</span></span>|<span data-ttu-id="08e7c-502">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-502">Boolean</span></span>|  
|<span data-ttu-id="08e7c-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="08e7c-503">CLUSTERED</span></span>|<span data-ttu-id="08e7c-504">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-504">Boolean</span></span>|  
|<span data-ttu-id="08e7c-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-505">TYPE</span></span>|<span data-ttu-id="08e7c-506">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-506">Int32</span></span>|  
|<span data-ttu-id="08e7c-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="08e7c-507">FILL_FACTOR</span></span>|<span data-ttu-id="08e7c-508">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-508">Int32</span></span>|  
|<span data-ttu-id="08e7c-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="08e7c-509">INITIAL_SIZE</span></span>|<span data-ttu-id="08e7c-510">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-510">Int32</span></span>|  
|<span data-ttu-id="08e7c-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="08e7c-511">NULLS</span></span>|<span data-ttu-id="08e7c-512">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-512">Int32</span></span>|  
|<span data-ttu-id="08e7c-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="08e7c-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="08e7c-514">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-514">Boolean</span></span>|  
|<span data-ttu-id="08e7c-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="08e7c-515">AUTO_UPDATE</span></span>|<span data-ttu-id="08e7c-516">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-516">Boolean</span></span>|  
|<span data-ttu-id="08e7c-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-517">NULL_COLLATION</span></span>|<span data-ttu-id="08e7c-518">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-518">Int32</span></span>|  
|<span data-ttu-id="08e7c-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-520">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-520">Int64</span></span>|  
|<span data-ttu-id="08e7c-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-521">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-522">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-522">String</span></span>|  
|<span data-ttu-id="08e7c-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-523">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-524">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-524">Guid</span></span>|  
|<span data-ttu-id="08e7c-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-525">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-526">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-526">Int64</span></span>|  
|<span data-ttu-id="08e7c-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-527">COLLATION</span></span>|<span data-ttu-id="08e7c-528">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-528">Int16</span></span>|  
|<span data-ttu-id="08e7c-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="08e7c-529">CARDINALITY</span></span>|<span data-ttu-id="08e7c-530">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="08e7c-530">Decimal</span></span>|  
|<span data-ttu-id="08e7c-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="08e7c-531">PAGES</span></span>|<span data-ttu-id="08e7c-532">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-532">Int32</span></span>|  
|<span data-ttu-id="08e7c-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-533">FILTER_CONDITION</span></span>|<span data-ttu-id="08e7c-534">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-534">String</span></span>|  
|<span data-ttu-id="08e7c-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-535">INTEGRATED</span></span>|<span data-ttu-id="08e7c-536">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="08e7c-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="08e7c-537">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="08e7c-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="08e7c-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="08e7c-539">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="08e7c-539">Tables</span></span>  
  
- <span data-ttu-id="08e7c-540">列</span><span class="sxs-lookup"><span data-stu-id="08e7c-540">Columns</span></span>  
  
- <span data-ttu-id="08e7c-541">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="08e7c-541">Procedures</span></span>  
  
- <span data-ttu-id="08e7c-542">Views</span><span class="sxs-lookup"><span data-stu-id="08e7c-542">Views</span></span>  
  
- <span data-ttu-id="08e7c-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="08e7c-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="08e7c-544">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="08e7c-544">Tables</span></span>  
  
|<span data-ttu-id="08e7c-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-545">ColumnName</span></span>|<span data-ttu-id="08e7c-546">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-547">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-548">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-548">String</span></span>|  
|<span data-ttu-id="08e7c-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-550">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-550">String</span></span>|  
|<span data-ttu-id="08e7c-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-551">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-552">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-552">String</span></span>|  
|<span data-ttu-id="08e7c-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-553">TABLE_TYPE</span></span>|<span data-ttu-id="08e7c-554">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-554">String</span></span>|  
|<span data-ttu-id="08e7c-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-555">TABLE_GUID</span></span>|<span data-ttu-id="08e7c-556">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-556">Guid</span></span>|  
|<span data-ttu-id="08e7c-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-557">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-558">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-558">String</span></span>|  
|<span data-ttu-id="08e7c-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-559">TABLE_PROPID</span></span>|<span data-ttu-id="08e7c-560">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-560">Int64</span></span>|  
|<span data-ttu-id="08e7c-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-561">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-562">DateTime</span></span>|  
|<span data-ttu-id="08e7c-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-563">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="08e7c-565">列</span><span class="sxs-lookup"><span data-stu-id="08e7c-565">Columns</span></span>  
  
|<span data-ttu-id="08e7c-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-566">ColumnName</span></span>|<span data-ttu-id="08e7c-567">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-568">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-569">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-569">String</span></span>|  
|<span data-ttu-id="08e7c-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-571">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-571">String</span></span>|  
|<span data-ttu-id="08e7c-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-572">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-573">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-573">String</span></span>|  
|<span data-ttu-id="08e7c-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-574">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-575">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-575">String</span></span>|  
|<span data-ttu-id="08e7c-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-576">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-577">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-577">Guid</span></span>|  
|<span data-ttu-id="08e7c-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-578">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-579">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-579">Int64</span></span>|  
|<span data-ttu-id="08e7c-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-581">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-581">Int64</span></span>|  
|<span data-ttu-id="08e7c-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="08e7c-583">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-583">Boolean</span></span>|  
|<span data-ttu-id="08e7c-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="08e7c-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="08e7c-585">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-585">String</span></span>|  
|<span data-ttu-id="08e7c-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="08e7c-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="08e7c-587">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-587">Int64</span></span>|  
|<span data-ttu-id="08e7c-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-588">IS_NULLABLE</span></span>|<span data-ttu-id="08e7c-589">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-589">Boolean</span></span>|  
|<span data-ttu-id="08e7c-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-590">DATA_TYPE</span></span>|<span data-ttu-id="08e7c-591">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-591">Int32</span></span>|  
|<span data-ttu-id="08e7c-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-592">TYPE_GUID</span></span>|<span data-ttu-id="08e7c-593">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-593">Guid</span></span>|  
|<span data-ttu-id="08e7c-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="08e7c-595">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-595">Int64</span></span>|  
|<span data-ttu-id="08e7c-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="08e7c-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="08e7c-597">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-597">Int64</span></span>|  
|<span data-ttu-id="08e7c-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="08e7c-599">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-599">Int32</span></span>|  
|<span data-ttu-id="08e7c-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="08e7c-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="08e7c-601">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-601">Int16</span></span>|  
|<span data-ttu-id="08e7c-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="08e7c-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="08e7c-603">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-603">Int64</span></span>|  
|<span data-ttu-id="08e7c-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="08e7c-605">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-605">String</span></span>|  
|<span data-ttu-id="08e7c-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="08e7c-607">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-607">String</span></span>|  
|<span data-ttu-id="08e7c-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="08e7c-609">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-609">String</span></span>|  
|<span data-ttu-id="08e7c-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="08e7c-611">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-611">String</span></span>|  
|<span data-ttu-id="08e7c-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="08e7c-613">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-613">String</span></span>|  
|<span data-ttu-id="08e7c-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-614">COLLATION_NAME</span></span>|<span data-ttu-id="08e7c-615">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-615">String</span></span>|  
|<span data-ttu-id="08e7c-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="08e7c-617">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-617">String</span></span>|  
|<span data-ttu-id="08e7c-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="08e7c-619">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-619">String</span></span>|  
|<span data-ttu-id="08e7c-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-620">DOMAIN_NAME</span></span>|<span data-ttu-id="08e7c-621">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-621">String</span></span>|  
|<span data-ttu-id="08e7c-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-622">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-623">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="08e7c-624">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="08e7c-624">Procedures</span></span>  
  
|<span data-ttu-id="08e7c-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-625">ColumnName</span></span>|<span data-ttu-id="08e7c-626">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="08e7c-628">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-628">String</span></span>|  
|<span data-ttu-id="08e7c-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="08e7c-630">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-630">String</span></span>|  
|<span data-ttu-id="08e7c-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="08e7c-632">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-632">String</span></span>|  
|<span data-ttu-id="08e7c-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="08e7c-634">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-634">Int16</span></span>|  
|<span data-ttu-id="08e7c-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="08e7c-636">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-636">String</span></span>|  
|<span data-ttu-id="08e7c-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-637">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-638">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-638">String</span></span>|  
|<span data-ttu-id="08e7c-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-639">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-640">DateTime</span></span>|  
|<span data-ttu-id="08e7c-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-641">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="08e7c-643">Views</span><span class="sxs-lookup"><span data-stu-id="08e7c-643">Views</span></span>  
  
|<span data-ttu-id="08e7c-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-644">ColumnName</span></span>|<span data-ttu-id="08e7c-645">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-646">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-647">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-647">String</span></span>|  
|<span data-ttu-id="08e7c-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-649">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-649">String</span></span>|  
|<span data-ttu-id="08e7c-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-650">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-651">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-651">String</span></span>|  
|<span data-ttu-id="08e7c-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="08e7c-653">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-653">String</span></span>|  
|<span data-ttu-id="08e7c-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-654">CHECK_OPTION</span></span>|<span data-ttu-id="08e7c-655">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-655">Boolean</span></span>|  
|<span data-ttu-id="08e7c-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="08e7c-656">IS_UPDATABLE</span></span>|<span data-ttu-id="08e7c-657">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-657">Boolean</span></span>|  
|<span data-ttu-id="08e7c-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08e7c-658">DESCRIPTION</span></span>|<span data-ttu-id="08e7c-659">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-659">String</span></span>|  
|<span data-ttu-id="08e7c-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-660">DATE_CREATED</span></span>|<span data-ttu-id="08e7c-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-661">DateTime</span></span>|  
|<span data-ttu-id="08e7c-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="08e7c-662">DATE_MODIFIED</span></span>|<span data-ttu-id="08e7c-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="08e7c-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="08e7c-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="08e7c-664">Indexes</span></span>  
  
|<span data-ttu-id="08e7c-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="08e7c-665">ColumnName</span></span>|<span data-ttu-id="08e7c-666">DataType</span><span class="sxs-lookup"><span data-stu-id="08e7c-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="08e7c-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-667">TABLE_CATALOG</span></span>|<span data-ttu-id="08e7c-668">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-668">String</span></span>|  
|<span data-ttu-id="08e7c-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="08e7c-670">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-670">String</span></span>|  
|<span data-ttu-id="08e7c-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-671">TABLE_NAME</span></span>|<span data-ttu-id="08e7c-672">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-672">String</span></span>|  
|<span data-ttu-id="08e7c-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="08e7c-673">INDEX_CATALOG</span></span>|<span data-ttu-id="08e7c-674">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-674">String</span></span>|  
|<span data-ttu-id="08e7c-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="08e7c-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="08e7c-676">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-676">String</span></span>|  
|<span data-ttu-id="08e7c-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-677">INDEX_NAME</span></span>|<span data-ttu-id="08e7c-678">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-678">String</span></span>|  
|<span data-ttu-id="08e7c-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="08e7c-679">PRIMARY_KEY</span></span>|<span data-ttu-id="08e7c-680">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-680">Boolean</span></span>|  
|<span data-ttu-id="08e7c-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="08e7c-681">UNIQUE</span></span>|<span data-ttu-id="08e7c-682">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-682">Boolean</span></span>|  
|<span data-ttu-id="08e7c-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="08e7c-683">CLUSTERED</span></span>|<span data-ttu-id="08e7c-684">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-684">Boolean</span></span>|  
|<span data-ttu-id="08e7c-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="08e7c-685">TYPE</span></span>|<span data-ttu-id="08e7c-686">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-686">Int32</span></span>|  
|<span data-ttu-id="08e7c-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="08e7c-687">FILL_FACTOR</span></span>|<span data-ttu-id="08e7c-688">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-688">Int32</span></span>|  
|<span data-ttu-id="08e7c-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="08e7c-689">INITIAL_SIZE</span></span>|<span data-ttu-id="08e7c-690">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-690">Int32</span></span>|  
|<span data-ttu-id="08e7c-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="08e7c-691">NULLS</span></span>|<span data-ttu-id="08e7c-692">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-692">Int32</span></span>|  
|<span data-ttu-id="08e7c-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="08e7c-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="08e7c-694">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-694">Boolean</span></span>|  
|<span data-ttu-id="08e7c-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="08e7c-695">AUTO_UPDATE</span></span>|<span data-ttu-id="08e7c-696">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-696">Boolean</span></span>|  
|<span data-ttu-id="08e7c-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-697">NULL_COLLATION</span></span>|<span data-ttu-id="08e7c-698">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-698">Int32</span></span>|  
|<span data-ttu-id="08e7c-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="08e7c-700">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-700">Int64</span></span>|  
|<span data-ttu-id="08e7c-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="08e7c-701">COLUMN_NAME</span></span>|<span data-ttu-id="08e7c-702">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-702">String</span></span>|  
|<span data-ttu-id="08e7c-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-703">COLUMN_GUID</span></span>|<span data-ttu-id="08e7c-704">GUID</span><span class="sxs-lookup"><span data-stu-id="08e7c-704">Guid</span></span>|  
|<span data-ttu-id="08e7c-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="08e7c-705">COLUMN_PROPID</span></span>|<span data-ttu-id="08e7c-706">Int64</span><span class="sxs-lookup"><span data-stu-id="08e7c-706">Int64</span></span>|  
|<span data-ttu-id="08e7c-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="08e7c-707">COLLATION</span></span>|<span data-ttu-id="08e7c-708">Int16</span><span class="sxs-lookup"><span data-stu-id="08e7c-708">Int16</span></span>|  
|<span data-ttu-id="08e7c-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="08e7c-709">CARDINALITY</span></span>|<span data-ttu-id="08e7c-710">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="08e7c-710">Decimal</span></span>|  
|<span data-ttu-id="08e7c-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="08e7c-711">PAGES</span></span>|<span data-ttu-id="08e7c-712">Int32</span><span class="sxs-lookup"><span data-stu-id="08e7c-712">Int32</span></span>|  
|<span data-ttu-id="08e7c-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="08e7c-713">FILTER_CONDITION</span></span>|<span data-ttu-id="08e7c-714">String</span><span class="sxs-lookup"><span data-stu-id="08e7c-714">String</span></span>|  
|<span data-ttu-id="08e7c-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="08e7c-715">INTEGRATED</span></span>|<span data-ttu-id="08e7c-716">ブール型</span><span class="sxs-lookup"><span data-stu-id="08e7c-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08e7c-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="08e7c-717">See also</span></span>

- [<span data-ttu-id="08e7c-718">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="08e7c-718">ADO.NET Overview</span></span>](ado-net-overview.md)
