#' Download and Load HNSCatlas Data
#'
#' This function downloads the HNSCatlas dataset if it is not already present
#' and loads it into the R environment as a Seurat object.
#'
#' @param destpath Directory or full file path where the dataset will be stored.
#'                 If a directory is provided, the dataset will be saved as "HNSCatlas.rds".
#'                 Default is the temporary directory.
#' @return A Seurat object containing the HNSCatlas dataset.
#' @examplesIf interactive()
#' HNSCatlas <- load_HNSCatlas()  # Uses temp directory
#' HNSCatlas <- load_HNSCatlas("/omics/odcf/analysis/OE0509_projects/hnscc/single_cell")
#'
#' @export
#' @importFrom utils download.file
load_HNSCatlas <- function(destpath = tempdir()) {

  # Ensure Seurat is installed
  if (!requireNamespace("Seurat", quietly = TRUE)) {
    stop("The 'Seurat' package is required but not installed. Please install it using install.packages('Seurat') or BiocManager::install('Seurat').")
  }

  # Increase timeout to allow large file download
  old_timeout <- getOption("timeout")
  options(timeout = max(600, old_timeout))  # Set to 600 seconds unless already higher

  # Define dataset URL
  url <- "https://hifis-storage.desy.de:2880/Helmholtz/E220-Radioonc_biol-DKFZ/HNSCC_Atlas.rds"

  # Check if user provided a directory or a full file path
  if (dir.exists(destpath)) {
    destfile <- file.path(destpath, "HNSCatlas.rds")  # Save in the directory
  } else {
    destfile <- destpath  # Assume it's a full file path
  }

  # Check if the file already exists locally
  if (!file.exists(destfile)) {
    message("Downloading HNSCatlas dataset...")

    # Attempt to download the file
    tryCatch({
      download.file(url, destfile, mode = "wb")
    }, error = function(e) {
      stop("Failed to download the dataset. Please check your internet connection or the repository link.")
    })

    message("Download completed successfully.")
  } else {
    message("Using locally cached HNSCatlas dataset.")
  }

  # Load the dataset
  if (file.exists(destfile)) {
    message("Loading HNSCatlas dataset into R environment...")
    return(readRDS(destfile))
  } else {
    stop("Error: The dataset could not be found after download. Please check your storage location.")
  }
}
